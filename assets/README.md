# assets

## portrait

Drop the headshot in here as **`portrait.jpg`** (`.png`, `.webp` and `.jpeg` also work —
the page tries each in that order).

Use the **original, unedited** studio shot on its plain white background. Do not cut
the background out first: the page does that itself at load time, flooding inward from
the frame edges through near-white pixels only. Because the flood is edge-connected,
a white shirt enclosed by a jacket is kept, while the backdrop goes transparent. Edge
pixels are un-premultiplied against white so no bright halo is left behind, and the
figure is cropped to its bounding box so it fills the hero column.

Requirements:

- Plain, evenly lit near-white background (RGB above ~236 on all channels).
- The subject must not be near-white all the way out to the frame edge.
- Same-origin only — the knockout reads pixels, so a cross-origin URL would taint
  the canvas and be skipped.

If no file is present, or the keying fails, the hero simply renders single-column
with no gap where the photo would be.
