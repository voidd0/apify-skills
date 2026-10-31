# Job postings from careers pages and job boards: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Indeed Jobs Scraper: Listings, Salary, Company Rating, Remote

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

## Wellfound Jobs Scraper: Salary, Equity, Stage

- Actor ID: `v0iddo/wellfound-jobs-scraper`
- Store page: https://apify.com/v0iddo/wellfound-jobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape startup jobs from Wellfound (AngelList Talent) by role and location, remote jobs or any search page: title, salary and equity ranges, experience, job type, remote policy, description, and the startup's size, stage, pitch and badges.

Example input:

```json
{
  "roles": [
    "Software Engineer"
  ],
  "locations": [
    "New York"
  ],
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `locations`, `workplace`, `salaryMin`, `salaryMax`, `salaryCurrency`, `equityMin`, `companyStage`, `postedAt`, `url`

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

## Instahyre Jobs Scraper: India Jobs, Skills

- Actor ID: `v0iddo/instahyre-jobs-scraper`
- Store page: https://apify.com/v0iddo/instahyre-jobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape India jobs from Instahyre: title, company, locations, skills, experience in years, posting date, employment type, the description, and the employer's size, founding year, tagline and website.

Example input:

```json
{
  "keywords": [
    "python"
  ],
  "locations": [
    "Bangalore"
  ],
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `experienceMin`, `experienceMax`, `skills`, `companyEmployees`, `postedDate`, `url`

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

## Reed Jobs Scraper: UK Jobs and Salaries

- Actor ID: `v0iddo/reed-jobs-scraper`
- Store page: https://apify.com/v0iddo/reed-jobs-scraper
- Price: $0.45 per 1,000 results, nothing per run

Scrape UK job postings from reed.co.uk: title, company, agency or employer, place, county, region, postcode, salary range with the period, job type, full or part time, remote or hybrid, posting and expiry dates, sector, skills and the description.

Example input:

```json
{
  "keywords": [
    "data analyst"
  ],
  "location": "London",
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `advertiser`, `location`, `salaryText`, `jobType`, `workingOption`, `postedAt`, `expiresAt`, `url`

## IIMJobs Scraper: India Finance and MBA Jobs

- Actor ID: `v0iddo/iimjobs-scraper`
- Store page: https://apify.com/v0iddo/iimjobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape India finance, sales, consulting, HR and operations jobs from iimjobs.com: company, locations, experience in years, salary in lakhs when shown, skills, category, posting time, the employer's AmbitionBox rating and profile, and the description.

Example input:

```json
{
  "keywords": [
    "finance manager"
  ],
  "locations": [
    "Mumbai"
  ],
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `experienceMin`, `experienceMax`, `salaryMinLakhs`, `salaryMaxLakhs`, `skills`, `companyRating`, `postedAt`, `url`

## Hirist Jobs Scraper: India Tech Jobs, Salary

- Actor ID: `v0iddo/hirist-jobs-scraper`
- Store page: https://apify.com/v0iddo/hirist-jobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape India tech jobs from hirist.tech: title, company, locations, experience in years, salary in lakhs when shown, skills, category, remote flag, posting time, the employer's AmbitionBox rating and profile, and the description.

Example input:

```json
{
  "keywords": [
    "python"
  ],
  "locations": [
    "Bangalore"
  ],
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `experienceMin`, `experienceMax`, `salaryMinLakhs`, `salaryMaxLakhs`, `skills`, `companyRating`, `postedAt`, `url`

## Jobs.ch & Jobup.ch Scraper: Swiss Jobs

- Actor ID: `v0iddo/jobs-ch-scraper`
- Store page: https://apify.com/v0iddo/jobs-ch-scraper
- Price: $0.90 per 1,000 results, nothing per run

Scrape Swiss job postings from jobs.ch and jobup.ch: title, company, address, canton, workload percent, employment type, position, posting dates, weekly hours, industry, category, skills, benefits, the employer's website and the description.

Example input:

```json
{
  "keywords": [
    "data analyst"
  ],
  "location": "Zürich",
  "site": "jobs.ch",
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `place`, `canton`, `workload`, `employmentType`, `position`, `postedAt`, `weeklyHours`, `industry`, `site`, `url`

## Computrabajo Scraper: LATAM Jobs and Salaries

- Actor ID: `v0iddo/computrabajo-scraper`
- Store page: https://apify.com/v0iddo/computrabajo-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape job postings from Computrabajo in 18 Latin American countries: title, company with rating, city, region, salary with currency and period, contract, schedule, remote or hybrid, education, experience, skills, industry and dates.

Example input:

```json
{
  "countries": [
    "mx"
  ],
  "keywords": [
    "contador"
  ],
  "location": "Monterrey",
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `city`, `country`, `salaryText`, `contractType`, `schedule`, `workMode`, `postedDate`, `url`

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

## Gupy Jobs Scraper: Brazil Job Vacancies

- Actor ID: `v0iddo/gupy-scraper`
- Store page: https://apify.com/v0iddo/gupy-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape Brazilian job postings from Gupy, the hiring system of most large employers in Brazil: title, company, city, state, job type, remote or hybrid, posted and deadline dates, requirements, hiring steps and the reason for the opening.

Example input:

```json
{
  "keywords": [
    "analista de dados"
  ],
  "state": "São Paulo",
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `city`, `state`, `jobTypeLabel`, `workplaceType`, `hiringReason`, `publishedAt`, `applicationDeadline`, `url`

## Pracuj.pl Scraper: Poland Jobs and Salaries

- Actor ID: `v0iddo/pracuj-pl-scraper`
- Store page: https://apify.com/v0iddo/pracuj-pl-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape Polish job postings from pracuj.pl: title, company, workplaces and address, salary per contract type, gross or net, position level, contract, schedule, remote or hybrid, category, technologies, requirements, benefits and dates.

Example input:

```json
{
  "keywords": [
    "księgowa"
  ],
  "location": "Warszawa",
  "includeDetails": true,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `salaryText`, `positionLevels`, `contractTypes`, `workModes`, `postedAt`, `expiresAt`, `url`

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
