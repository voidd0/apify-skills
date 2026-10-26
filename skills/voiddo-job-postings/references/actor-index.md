# Job postings from careers pages and job boards: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Indeed Jobs Scraper: Salary, Company Rating, Remote, Dates

- Actor ID: `v0iddo/indeed-scraper`
- Store page: https://apify.com/v0iddo/indeed-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape Indeed.com job search results: title, company and its rating, location, remote or hybrid, salary range and period where the employer shows it, job types, posting date, urgent and easy apply flags, snippet and job URL.

Example input:

```json
{
  "query": "data analyst",
  "location": "Remote",
  "datePosted": "any",
  "jobType": "",
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `remote`, `salary`, `salaryMin`, `salaryMax`, `salaryPeriod`, `postedAt`, `jobTypes`, `sponsored`, `jobUrl`

## Remote Jobs Scraper: RemoteOK, WWR, Jobicy

- Actor ID: `v0iddo/remote-jobs-scraper`
- Store page: https://apify.com/v0iddo/remote-jobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape remote jobs from Remote OK, We Work Remotely, Jobicy, Working Nomads and Arbeitnow in one feed: title, company, location, eligible countries, salary, job type, level, tags, posted date and description.

Example input:

```json
{
  "keywords": [
    "engineer",
    "developer"
  ],
  "maxItems": 20,
  "maxJobsPerBoard": 6
}
```

Output fields: `title`, `company`, `location`, `salaryMin`, `salaryMax`, `salaryCurrency`, `sourceName`, `publishedAt`, `url`

## Workday Jobs Scraper: Salary, Dates, Remote

- Actor ID: `v0iddo/workday-jobs-scraper`
- Store page: https://apify.com/v0iddo/workday-jobs-scraper
- Price: $0.90 per 1,000 results, nothing per run

Collect every open job from any Workday careers site (myworkdayjobs.com): title, location, country, remote or on site, employment type, real posting date, pay range where the posting states it, and the description as plain text.

Example input:

```json
{
  "companies": [
    "https://nvidia.wd5.myworkdayjobs.com/NVIDIAExternalCareerSite",
    "https://salesforce.wd12.myworkdayjobs.com/External_Career_Site"
  ],
  "includeDescription": true,
  "maxItems": 50,
  "maxJobsPerCompany": 25
}
```

Output fields: `ats`, `company`, `title`, `department`, `location`, `remote`, `workplaceType`, `employmentType`, `postedAt`, `salaryMin`, `salaryMax`, `salaryCurrency`, `url`

## Greenhouse, Lever, Workday & Ashby Jobs Scraper: Careers API

- Actor ID: `v0iddo/ats-jobs-scraper`
- Store page: https://apify.com/v0iddo/ats-jobs-scraper
- Price: $1.20 per 1,000 results, nothing per run

Collect public job postings from Greenhouse, Lever, Workday, Workable, Ashby, Recruitee, Personio and BambooHR with one consistent schema.

Example input:

```json
{
  "companies": [
    "https://job-boards.greenhouse.io/discord",
    "https://jobs.lever.co/spotify",
    "https://apply.workable.com/huggingface"
  ],
  "includeDescription": true,
  "maxItems": 50,
  "maxJobsPerCompany": 20
}
```

Output fields: `ats`, `company`, `title`, `department`, `location`, `remote`, `workplaceType`, `employmentType`, `postedAt`, `salaryMin`, `salaryMax`, `salaryCurrency`, `url`

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
