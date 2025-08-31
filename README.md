# HEIC → JPG/PNG/WebP Bulk Converter

One-file web app for converting HEIC photos for marketplaces (eBay, Vinted, Depop). Runs entirely in your browser.

## Use
1. Open the site.
2. Drag in HEIC files.
3. Pick a preset or set your own format/quality/size.
4. (Optional) Upload a CSV to inject SKUs into filenames.
5. Click **Convert & Zip**.

## Features
- Presets: eBay (JPG 85, 1600px), Vinted (JPG 85, 2048px), Depop (JPG 90, 2000px)
- Filename tokens: `{base}`, `{index}`, `{date}`, `{time}`, `{sku}`
- CSV mapping: `original,new` or `name,sku`
- Live progress, cancel button, per-item removal
- Light/Dark theme with **Auto** mode (follows system)
- Offline after first load (PWA-lite)

## Deploy on Vercel
No build step: just `index.html`. Add this `vercel.json` to avoid stale caching:

```json
{
  "cleanUrls": true,
  "headers": [
    {
      "source": "/index.html",
      "headers": [
        {
          "key": "Cache-Control",
          "value": "no-cache"
        }
      ]
    }
  ]
}
```

### Steps
1. Push these files (`index.html`, `vercel.json`, `README.md`) to a GitHub repo.
2. Go to https://vercel.com → **Add New Project** → import the repo.
3. Framework Preset: **Other**. Build Command: *None*. Output Dir: */* or blank.
4. **Deploy** → open the URL.
