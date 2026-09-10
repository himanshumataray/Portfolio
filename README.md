# Portfolio — Himanshu Mataray

Single-page portfolio site, styled as an investment memo. Static HTML with no build
step or dependencies: `index.html` is the whole site (CSS is inlined; fonts load
from Google Fonts).

## Local preview

```
python3 -m http.server 8000
```

Then open http://localhost:8000

## Deploying with GitHub Pages

Settings → Pages → Build and deployment → Deploy from a branch, then pick the
branch and the `/ (root)` folder.

## Note

The header and footer link to `resume.pdf` at the repo root. Add that file before
publishing, or the links will 404.
