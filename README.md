# Haze Watch

Static single-page app (no build step). Files:

- `index.html` - the whole app (HTML, CSS and JS in one file)
- `vercel.json` - clean URLs and basic headers

## Data sources (fetched in the browser, no API keys)

- Haze (PSI, PM2.5, PM10, Singapore only): NEA via data.gov.sg
  `https://api-open.data.gov.sg/v2/real-time/api/psi`
  (falls back to `https://api.data.gov.sg/v1/environment/psi`)
- Weather for every city: Open-Meteo `https://api.open-meteo.com/v1/forecast`

If a request fails, the page shows a notice and a button to preview the layout
with clearly labelled placeholder values.

## Deploy

Vercel dashboard: Add New > Project > import the repo (or drag this folder in).
Framework preset: Other. Build command: none. Output directory: leave blank.

CLI:

    npm i -g vercel
    vercel --prod

Local preview: `npx serve .`
