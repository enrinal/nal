---
title: "How this site works"
date: 2026-10-07
description: "A small VPS, Caddy, Hugo, and a GitHub Action that can only write one folder."
---

I wanted a place to keep my resume and write things down. The requirements were short: Markdown in, static HTML out, no database, nothing to patch every month. This is the setup I ended up with.

## The pieces

- **Server:** a small Tencent Cloud VPS running Debian 13.
- **Web server:** [Caddy](https://caddyserver.com). It serves a folder of HTML files and handles HTTPS certificates by itself.
- **Site generator:** [Hugo](https://gohugo.io). No theme, just four small layout files.
- **Deploy:** a GitHub Action that builds the site and copies it to the server with `rsync`.

Source is at [github.com/enrinal/nal](https://github.com/enrinal/nal).

## Caddy instead of nginx

For a static site with a couple of domains, Caddy's config is about as short as it gets:

```
enrinal.is-a.dev {
	root * /var/www/portfolio
	file_server
}
```

That's the whole thing. Caddy sees the domain name, gets a Let's Encrypt certificate, and renews it. With nginx I would also be setting up certbot and a renewal timer. nginx is the better choice for heavy traffic or advanced features, but neither applies here.

## Hugo without a theme

Hugo themes are nice, but they come with a lot of code I'd have to read when something breaks. The whole site is one base template with inline CSS, a home page, a post list, and a post page. The resume is a plain Markdown file. Writing a post is creating a file under `content/blog/` and pushing.

Light and dark mode come from `prefers-color-scheme`. The "Save as PDF" button on the resume is just `window.print()` plus a print stylesheet, so I don't have to keep a separate PDF in sync.

## Deploying without handing out root

This is the part I cared about most. The GitHub Action needs SSH access to the server, and an SSH key stored in CI is a key I should expect to leak one day. So the key it gets can do exactly one thing.

On the server there is a `deploy` user with no password. Its `authorized_keys` entry looks like this:

```
command="/usr/bin/rrsync -wo /var/www/portfolio",restrict ssh-ed25519 AAAA... deploy
```

- `rrsync` is a wrapper that ships with rsync. Whatever command the client sends, the only thing that runs is rsync, and only inside `/var/www/portfolio`.
- `-wo` makes it write-only, so the key can't read anything back from the server.
- `restrict` turns off port forwarding, agent forwarding, and a terminal.

If you try to open a shell with that key, you get this and nothing else:

```
/usr/bin/rrsync error: SSH_ORIGINAL_COMMAND does not run rsync
```

The workflow itself is short:

```yaml
- run: hugo --minify
- name: rsync to VPS
  run: |
    printf '%s\n' "$DEPLOY_SSH_KEY" > ~/.ssh/deploy_key
    echo "43.173.27.95 ssh-ed25519 AAAA..." > ~/.ssh/known_hosts
    rsync -rlcz --delete -e "ssh -i ~/.ssh/deploy_key" public/ deploy@43.173.27.95:
```

The server's host key is pinned in the workflow, so the Action won't blindly trust whatever answers on that IP. I use `-c` (checksum) because Hugo rewrites every file on each build, so comparing modification times would copy everything every time.

## What I skipped

No comments, no analytics, no search, no tags. If I ever need them I'll add them. For now: write Markdown, push, and it's live about a minute later.
