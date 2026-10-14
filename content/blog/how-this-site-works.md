---
title: "How this site works"
date: 2026-10-07
description: "A small VPS, Caddy, Hugo, and a GitHub Action."
---

I wanted a place to keep my resume and write things down. The requirements were short: Markdown in, static HTML out, no database, nothing to patch every month. This is the setup I ended up with.

## The pieces

- **Server:** a small Tencent Cloud VPS running Debian 13.
- **Web server:** [Caddy](https://caddyserver.com). It serves a folder of HTML files and handles HTTPS certificates by itself.
- **Site generator:** [Hugo](https://gohugo.io). No theme, just four small layout files.
- **Deploy:** a GitHub Action that builds the site and copies it to the server with `rsync`.

Source is at [github.com/enrinal/nal](https://github.com/enrinal/nal).

## What I skipped

No comments, no analytics, no search, no tags. If I ever need them I'll add them. For now: write Markdown, push, and it's live about a minute later.
