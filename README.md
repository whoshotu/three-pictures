# three.pictures

> A free, private, browser-based photo booth. Three shots. One strip.

![three.pictures booth](https://img.shields.io/badge/status-MVP-green?style=flat-square) ![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)

---

## What it is

A single-file HTML photo booth that runs entirely in the browser. No backend. No accounts. No data ever leaves your device unless you choose to order a print.

- **Three shots** with countdown timer
- **Four looks**: Natural, Chrome, Faded, B&W
- **Film strip** output with sprocket holes and timestamp
- **Save strip** as JPEG — canvas-composited with filter baked in
- **Order a Print** flow — gated behind a consent modal (print API hookup ready)
- **100% client-side** — webcam feed processed via Canvas API, no uploads

---

## Stack

| Layer | Choice | Why |
|---|---|---|
| Runtime | Vanilla JS + Canvas API | Zero dependencies, runs anywhere |
| Webcam | `getUserMedia()` | Native browser API |
| Fonts | DM Mono + Playfair Display + DM Sans | Human, analog feel |
| Deployment | Any static host | One file, no build step |

---

## Run locally

```bash
# Just open the file — no server needed for most browsers
open booth.html

# Or serve it (required for camera on some browsers)
npx serve .
# then open http://localhost:3000/booth.html
```

---

## Deployment

Drop `booth.html` on any static host:

- **Netlify** — drag and drop the file
- **Vercel** — `vercel --prod`
- **GitHub Pages** — enable in repo settings → Pages → main branch
- **Cloudflare Pages** — connect repo, no build command needed

---

## Print API hookup

The print modal is already wired. To connect a real printer:

1. Sign up for [Gelato](https://gelato.com) or [Printful](https://printful.com)
2. Replace the `// TODO` comment in the `btn-mconfirm` handler with your API call
3. Pass `shots[0..2]` (base64 data URLs) or the export canvas blob

---

## Roadmap

- [ ] Share strip via unique URL (needs lightweight backend)
- [ ] Event mode — QR code for group sessions
- [ ] Custom strip branding / text overlay
- [ ] AI face filter layer (TensorFlow.js)
- [ ] PWA / installable app

---

## License

MIT — do whatever you want with it.

---

*Built by [@whoshotu](https://github.com/whoshotu)*
