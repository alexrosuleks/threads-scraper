# Threads Scraper: Threads Scraper API for Python & Node.js (2026)

Scrape public Threads profiles, posts and replies: text, likes, replies, reposts, media and follower counts. No login or cookies needed. Export to JSON or CSV.

**[▶ Try the Threads Scraper free on Scrapely](https://scrape.ly/store/echofield/threads-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Threads data with the [Threads Scraper](https://scrape.ly/store/echofield/threads-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the threads scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Threads scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/threads-scraper) or from your code with the SDK.
- **Structured threads data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $2.50 per 1,000 result results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Threads changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Threads data can you extract?

Scrape public Threads profiles, posts and replies: text, likes, replies, reposts, media and follower counts. No login or cookies needed. Export to JSON or CSV.

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/threads-scraper').call({"mode": "user", "usernames": ["zuck"], "max_posts": 10, "search_filter": "top", "search_language": "english", "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/threads-scraper').call(run_input={ "mode": "user", "usernames": [ "zuck" ], "max_posts": 10, "search_filter": "top", "search_language": "english", "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~threads-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "mode": "user",
  "usernames": [
    "zuck"
  ],
  "max_posts": 10,
  "search_filter": "top",
  "search_language": "english",
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [Threads Scraper page](https://scrape.ly/store/echofield/threads-scraper).

## Pricing

**$2.50 per 1,000 result results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/threads-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Threads with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Threads with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a threads scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~threads-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Threads legal?** This scraper collects publicly available data. Check Threads's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related Threads scrapers

- [Threads Search Scraper](https://github.com/alexrosuleks/threads-search-scraper): Search Threads by keyword and scrape public posts and user profiles: text, likes, replies, reposts and followers. No…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** threads scraper, threads scraper, threads scraper api, threads scraper python, threads scraper node.js,
scrape threads, threads data extraction, threads crawler, threads api, export threads data to csv, threads-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/threads-scraper).
