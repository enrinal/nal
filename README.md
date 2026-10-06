# nal

Personal site: online resume (`/`) and blog (`/blog`), built with [Hugo](https://gohugo.io) and served by Caddy on a VPS.

## Write a post

1. Copy `content/blog/_template.md` to `content/blog/<slug>.md`.
2. Set `title` and `date`, delete `draft: true`, write in Markdown.
3. Push to `main`. GitHub Actions builds the site and rsyncs it to the server.

Preview locally with `hugo server -D` and open http://localhost:1313.

## Edit the resume

Edit `content/_index.md`. The "Save as PDF" button prints the page with a print stylesheet.
