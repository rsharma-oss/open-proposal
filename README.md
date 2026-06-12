# Open Proposal Builder

A free, open-source SEO/AEO proposal generator. No server, no login, no build step — a single HTML file you run locally.

Built for agencies and consultants who want to present SEO + AI visibility strategy proposals to clients with their own branding.

## What it does

- 8-step wizard to fill in agency branding, client info, SEO data, AI visibility metrics, keywords, pricing, and timeline
- Generates a 12-slide Reveal.js presentation as a standalone HTML file
- "Powered by" branding in every slide header is replaced with **your** agency name and logo
- All data persists in `localStorage` — close the tab and come back, your data is still there
- **Optional DataForSEO auto-fill** — pull live keyword counts and organic traffic for the client and competitors in Step 4 instead of typing them by hand

## DataForSEO auto-fill (optional)

Step 4 (SEO Data) includes an **Auto-fill from DataForSEO** panel. Paste your DataForSEO
API token (the base64 of `login:password` shown in your DataForSEO dashboard) and click
**Fetch from DataForSEO** — it fills **Org. Keywords** and **Monthly Traffic** for the client
domain (from Step 2) and any competitor domains you've entered, using the DataForSEO Labs
`domain_rank_overview` endpoint. Calls run directly from your browser (DataForSEO supports CORS).

- Your token is stored only in this browser, under its own `pb_dfs_auth` key. It is **never**
  written into the proposal data and **never** appears in the generated/downloaded HTML you send
  to clients.
- **DR** and **Ref. Domains** aren't available from this source — enter those manually (e.g. Ahrefs).
- Metrics default to the US / English market.

## How to use

1. Download `index.html`
2. Open it in any browser (double-click, or `python3 -m http.server 8080` then visit `localhost:8080`)
3. Fill in the wizard steps
4. Click **Preview in New Tab** or **Download HTML**

## Exporting to PDF

1. Open the generated proposal in Chrome
2. Add `?print-pdf` to the URL
3. `Cmd+P` → Save as PDF → Layout: Landscape, Margins: None, ✓ Background graphics

## What's in each slide

| # | Slide |
|---|-------|
| 1 | Cover — headline + subline |
| 2 | The Opportunity — what AI search means for their category |
| 3 | The Gaps — 4 reasons they're invisible today |
| 4 | SEO Benchmark — DR/keywords/traffic vs competitors |
| 5 | AI Visibility — prompt tracking, scores, cited sources |
| 6 | Keyword Strategy — 3 clusters with target terms |
| 7 | Content Plan — comparison content + competitor capture |
| 8 | Deliverables — what's included each month |
| 9 | Case Study & Testimonials |
| 10 | Measuring Success — GSC + GA4 + your tracking tool |
| 11 | Investment & Timeline — 4-phase plan + pricing |
| 12 | About Us — booking link + agency website |

## Customisation

All styling uses CSS variables. The accent color is derived from a single hex input — background tint, border, and dark variant are computed automatically.

The template is a plain JavaScript string in `index.html`. Search for `fillTemplate()` to edit slide content directly.

## License

MIT — use it, fork it, white-label it.
