# PetDex — Deployment Guide

## Files
- `index.html` — the entire application (one file)
- `vercel.json` — routing config for clean URLs

## Deploy to Vercel (5 minutes, free)

1. Go to vercel.com and sign up with GitHub
2. Create a new GitHub repo, upload both files
3. In Vercel: "Add New Project" → import your repo → Deploy
4. Add your custom domain (e.g. petdex.io) in Vercel settings

## URLs after deployment

| URL | What it shows |
|-----|--------------|
| `petdex.io` | Full landing page + embedded demo |
| `petdex.io/kiosk` | Full-screen kiosk mode (use on tablet) |
| `petdex.io/widget` | Compact embed for retailer websites |

## URL parameters

| Parameter | Example | Effect |
|-----------|---------|--------|
| `?mode=kiosk` | `/index.html?mode=kiosk` | Kiosk mode |
| `?mode=widget` | `/index.html?mode=widget` | Widget mode |
| `?reset=300` | `/kiosk?reset=300` | Auto-reset after 300s inactivity |
| `?color=1D9E75` | `/widget?color=185FA5` | Override brand color (hex, no #) |

## Kiosk setup (in-store tablet)

1. Open `petdex.io/kiosk` in Chrome or Safari
2. Enable full-screen / kiosk mode in the browser settings
3. The app auto-resets after 5 minutes of inactivity (configurable)
4. No app install. No IT department needed.

## Embedding on a retailer website

Paste this snippet anywhere on the retailer's site:

```html
<iframe
  src="https://petdex.io/widget?color=YOUR_BRAND_COLOR"
  width="420"
  height="640"
  frameborder="0"
  style="border-radius:16px; border:1px solid #E5E7EB;"
  title="Find your perfect pet">
</iframe>
```

Replace `YOUR_BRAND_COLOR` with the retailer's hex color (no `#`).
