# Ceiling Guru

Website for Ceiling Guru — PVC, soffit and WPC ceilings, fully installed, serving Penang, Kulim and Kedah.

A single static page (Chinese / English / Bahasa Melayu). No build step: upload the files and it works.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The whole site: layout, styles, scripts and all three languages |
| `favicon.svg` | Browser tab icon (the Ceiling Guru logo) |
| `img/` | Product colour photos (`pvc-*`, `sof-*`, `wpc-*`), 3D panel textures (`tex-*`) and soffit reference images (`g-*`) |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Put it online with GitHub Pages

1. Create a new repository on GitHub, for example `ceiling-guru`.
2. Upload everything in this folder (keep the `img` folder as it is) to the repository's main branch.
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main** and folder **/ (root)**, then **Save**.
5. After a minute or two the site is live at `https://<your-username>.github.io/ceiling-guru/`.

To use your own domain (for example `ceilingguru.my`), enter it under **Settings → Pages → Custom domain** and follow GitHub's DNS instructions.

## Before you go live

**WhatsApp number.** In `index.html`, search for `WA_NUMBER` and put your number in, digits only with the country code:

```js
const WA_NUMBER = "60123456789";
```

Every WhatsApp button and the price estimator's "send this estimate" button then open WhatsApp with a ready-written message.

**Still to add when confirmed:** warranty and after-sales details, and photos of your own finished jobs (the soffit gallery currently uses supplier reference images and says so on the page).

## Changing things later

- **Prices:** search `PRICES` in `index.html`. Each product has `[150–200 sq ft rate, 201 sq ft and up rate]`. Also update the matching numbers in the text if you change them.
- **Wording:** all text for the three languages is in the `I18N` block in `index.html` (`zh`, `en`, `ms`).
- **Colour textures:** replace the matching `img/tex-<colour>.jpg` (for the 3D panel) and `img/<colour>.jpg` (the round colour button). Keep the same file name.

## Notes

- The 3D panels use three.js loaded from cdnjs; fonts load from Google Fonts. Both need an internet connection, which visitors will have.
- Opening `index.html` by double-clicking may not show the 3D textures, because browsers block local image loading for 3D. It works once the site is on GitHub Pages, or with a local server: `python3 -m http.server` in this folder, then open `http://localhost:8000`.
