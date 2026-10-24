# Web pages, documents and media files: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Sitemap URL Extractor: Robots.txt and Sitemap Index to URLs

- Actor ID: `v0iddo/sitemap-url-extractor`
- Store page: https://apify.com/v0iddo/sitemap-url-extractor
- Price: $1.00 per 1,000 results, nothing per run

Sitemap URL extractor and sitemap index crawler.

Example input:

```json
{
  "domains": [
    "stripe.com",
    "shopify.com",
    "vercel.com"
  ],
  "maxUrlsPerDomain": 20
}
```

Output fields: `domain`, `url`, `lastmod`, `changefreq`, `priority`, `source`
