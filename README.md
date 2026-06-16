# 360CarMart — Dealer Pitch Deck

Interactive, **mobile + web optimised** pitch deck for 360CarMart, Singapore's 3D-first
car marketplace. Self-contained static page with live, orbitable 3D car models (Three.js).

## Run locally
The 3D needs to be served over HTTP (not opened as a `file://`):

```bash
npx serve .            # or: python3 -m http.server 8080
```

Then open the printed URL.

## Navigate
- **← / →**, space, or **swipe** to move between slides
- Side **dots** jump to a slide; **F** toggles fullscreen (desktop)
- On the 3D slides: **drag** to orbit, **scroll/pinch** to zoom, tap a car to switch

## Deploy (Vercel)
```bash
vercel --prod
```

## Structure
- `index.html` — the entire deck (HTML + CSS + Three.js via CDN import map)
- `models/*.glb` — web-optimised 3D cars (meshopt geometry + WebP textures, ~2 MB each)
- `images/cars/*.jpg` — posters / 3D fallbacks

3D models were generated with the `car-3d-product` workflow (Meshy `image_to_3d` /
`multi_image_to_3d` → `gltf-transform` compression). The Ferrari F8 uses a multi-view
capture for sharper detail.
