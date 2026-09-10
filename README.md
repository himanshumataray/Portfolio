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

## Deploying

### Vercel

No build step — `vercel.json` configures it as a static site served from the repo
root, with cache and security headers.

1. Go to [vercel.com/new](https://vercel.com/new) and import this repository. It is
   private, so grant Vercel access to it when prompted.
2. Framework Preset **Other**, Root Directory `./`. Leave build command and output
   directory empty.
3. Deploy.

`claude/portfolio-website-styling-gagtoy` is the repository's default branch, so it
is the production branch and every push to it redeploys.

From a local clone instead: `npx vercel --prod`.

### GitHub Pages

Settings → Pages → Build and deployment → Deploy from a branch, then pick the
branch and the `/ (root)` folder.

## Adding the headshot

Drop the original, unedited studio headshot at `assets/portrait.jpg` (`.png`, `.webp`
and `.jpeg` also work). Do **not** remove the white background first — the page keys
it out in the browser on load and crops the figure to fit the hero. See
[`assets/README.md`](assets/README.md) for how the keying works and what it needs.

With no photo present the hero renders single-column, so the page is never left with
a gap where the portrait would be.

## Resume

The hero and footer carry a "Resume (PDF)" link pointing at
`Himanshu-Mataray-CV.pdf` in the repo root. The filename is deliberately
descriptive rather than generic, so it still identifies its owner once someone
has saved it.

To replace the CV, overwrite that file. To change the filename, update the `href`
on both `.resume-link` anchors — the availability check below reads the path off
the link itself, so there is no second place to edit.

If the file is ever missing, the page asks the server for it on load and hides
both links rather than leaving a dead link behind; restoring the file brings them
back. A network or protocol error is deliberately not treated as "missing", so a
transient failure can never hide a link that really works. With JavaScript
disabled the links are always rendered.
