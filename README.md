# Portfolio — Himanshu Mataray

Single-page portfolio site — dark editorial treatment with scroll-driven motion.
Static HTML with no build step or dependencies: `index.html` is the whole site
(CSS and JS are inlined; fonts load from Google Fonts).

Motion is progressive: scroll reveals are only armed once the script runs, so with
JavaScript disabled every section renders visible rather than blank. All animation
is disabled under `prefers-reduced-motion`.

## Local preview

```
python3 -m http.server 8000
```

Then open http://localhost:8000

## Deploying with GitHub Pages

Settings → Pages → Build and deployment → Deploy from a branch, then pick the
branch and the `/ (root)` folder.

## Adding the headshot

Drop the original, unedited studio headshot at `assets/portrait.jpg` (`.png`, `.webp`
and `.jpeg` also work). Do **not** remove the white background first — the page keys
it out in the browser on load and crops the figure to fit the hero. See
[`assets/README.md`](assets/README.md) for how the keying works and what it needs.

With no photo present the hero renders single-column, so the page is never left with
a gap where the portrait would be.

## Note

The header and footer link to `resume.pdf` at the repo root. Add that file before
publishing, or the links will 404.
