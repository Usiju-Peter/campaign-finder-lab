# campaignfinder lab

Every campaign on Content Rewards Discover with its budget left, creator count and pay rates, refreshed every 4 hours.

- `scraper/scrape.js list|details` reads the site with Playwright (Chromium; set `BROWSER_CHANNEL=msedge` to use Edge on Windows).
- `scraper/build.py candidates|build` parses the pages into `public/data/campaigns.json`, keeps a compact snapshot per run in `data/history/` and the first-seen date of each campaign in `data/first_seen.json`.
- `.github/workflows/refresh.yml` runs both every 4 hours and commits the new data; Vercel serves `public/`.
- `public/index.html` is the dashboard (generated from `scraper/page.html`).

Experimental copy of [campaign-finder](https://github.com/Usiju-Peter/campaign-finder) for trying new designs and features. Live at https://campaign-finder-lab.vercel.app. It has its own data refresh every 4 hours (at :47, 30 minutes after the main site).
