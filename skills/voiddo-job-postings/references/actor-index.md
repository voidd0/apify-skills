# Job postings from careers pages and job boards: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Greenhouse Jobs API and Scraper: Job Postings by Company

- Actor ID: `v0iddo/greenhouse-public-jobs`
- Store page: https://apify.com/v0iddo/greenhouse-public-jobs
- Price: $0.20 per 1,000 results, nothing per run

Greenhouse jobs API and scraper.

Example input:

```json
{
  "companies": [
    "stripe",
    "airbnb",
    "vercel"
  ],
  "maxJobsPerCompany": 20
}
```

Output fields: `company`, `companyName`, `jobId`, `internalJobId`, `title`, `location`, `departments`, `offices`, `language`, `requisitionId`, `firstPublished`, `updatedAt`

## Ashby Jobs API and Scraper: Job Postings by Company

- Actor ID: `v0iddo/ashby-public-jobs`
- Store page: https://apify.com/v0iddo/ashby-public-jobs
- Price: $1.70 per 1,000 results, nothing per run

Ashby jobs API and scraper.

Example input:

```json
{
  "companies": [
    "linear",
    "posthog",
    "notion"
  ]
}
```

Output fields: `company`, `jobId`, `title`, `location`, `employmentType`, `team`, `department`, `applyUrl`, `publishedAt`, `updatedAt`, `isRemote`, `descriptionPlain`

## Lever Jobs API and Scraper: Job Postings by Company

- Actor ID: `v0iddo/lever-public-jobs`
- Store page: https://apify.com/v0iddo/lever-public-jobs
- Price: $0.20 per 1,000 results, nothing per run

Lever jobs API and scraper.

Example input:

```json
{
  "companies": [
    "spotify",
    "palantir"
  ],
  "maxJobsPerCompany": 20
}
```

Output fields: `company`, `jobId`, `title`, `team`, `department`, `location`, `allLocations`, `country`, `workplaceType`, `commitment`, `createdAtMs`, `createdAt`
