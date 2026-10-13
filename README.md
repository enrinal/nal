# nal

Personal site at https://enrinal.is-a.dev: about page (`/`), printable resume (`/resume/`), and blog (`/blog/`), built with [Hugo](https://gohugo.io) and served by Caddy on a VPS.

## Write a post

1. Copy `content/blog/_template.md` to `content/blog/<slug>.md`.
2. Set `title` and `date`, delete `draft: true`, write in Markdown.
3. Push to `main`. GitHub Actions builds the site and rsyncs it to the server.

Preview locally with `hugo server -D` and open http://localhost:1313.

## Edit the resume

Edit `data/resume.yaml`. The home page and `/resume/` both render from it, so they never drift apart. Keep the phone number out: this file is published.

The "Save as PDF" button on `/resume/` prints an A4 page with a print stylesheet.
