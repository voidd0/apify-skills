# Ads from the Meta Ad Library: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Facebook Ad Library Scraper

- Actor ID: `v0iddo/facebook-ads-library-scraper`
- Store page: https://apify.com/v0iddo/facebook-ads-library-scraper
- Price: $0.50 per 1,000 results, nothing per run

Collect public ads from the Meta Ad Library by keyword, advertiser Page ID or Ad Library link: ad text, headline, landing page, button, images and videos, dates, platforms and version count, plus spend and reach ranges where Meta publishes them.

Example input:

```json
{
  "searchTerms": [
    "nike"
  ],
  "country": "US",
  "activeStatus": "active",
  "maxItems": 20
}
```

Output fields: `adArchiveId`, `pageName`, `isActive`, `startDate`, `endDate`, `platforms`, `body`, `title`, `ctaText`, `linkUrl`, `displayFormat`, `imageUrls`, `adLibraryUrl`
