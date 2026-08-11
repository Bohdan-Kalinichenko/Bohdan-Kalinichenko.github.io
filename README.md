# Bohdan-Kalinichenko.github.io

A single-page academic site, styled after ddiazvil.com. Light/dark mode.
All the text is loaded at runtime from `content.md` — you never need to
touch `index.html` again for normal updates.

## How it's structured

```
index.html      the page shell + styling + loader script (edit rarely)
content.md      your actual content: bio, papers, teaching, contact (edit this)
assets/
  marked.min.js Markdown parser (MIT licensed) that renders content.md
profileBK.jpeg  your photo — keep this filename, or update the path in content.md
CV_BK.pdf       your CV — add this file, referenced from content.md
```

## Editing your content

Open `content.md` and edit directly:

- The first `# Heading` becomes your name at the top of the page.
- The italic line right under it becomes the small tagline under your name.
- The first image becomes your sidebar photo.
- Each `## Section` becomes a section people can jump to from the sidebar
  nav (About / Research / Teaching / Code / Contact) — the anchor id is
  generated automatically from the heading text, so keep the heading names
  (`## About`, `## Research`, `## Teaching`, `## Code`, `## Contact`) as-is
  unless you also update the links in `index.html`'s `.section-nav`.
- For each paper, write it as `### Paper Title`, then a `> ` blockquote
  right after it — that blockquote becomes the collapsible "Abstract" box.
  Add a link button above it (see the `paper1.pdf` example in `content.md`)
  for a PDF / slides / code link.

## Running it locally

Because the page fetches `content.md` with `fetch()`, opening `index.html`
directly from disk (`file://`) will fail in most browsers (CORS). Run a
tiny local server instead:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Publishing

Just commit and push to the `main` branch — GitHub Pages serves it
automatically at `https://bohdan-kalinichenko.github.io`.

```
git add .
git commit -m "Update content"
git push
```

## To finish setting this up

1. Replace the placeholder paper titles/abstracts/PDF links in `content.md`
   with your real papers.
2. Add your real `CV_BK.pdf` to the repo root (or update the link).
3. Update the LinkedIn URL in `index.html` (search for `YOUR-LINKEDIN-HANDLE`).
4. Fill in the Teaching and Code sections with your actual courses/projects.
5. Make sure `profileBK.jpeg` is in the repo root (it already is in your
   current site, so nothing to do there).
