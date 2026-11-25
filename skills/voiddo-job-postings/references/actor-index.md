# Job postings from careers pages and job boards: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

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

## Kariyer Scraper: Kariyer.net Turkey Job Listings

- Actor ID: `v0iddo/kariyer-scraper`
- Store page: https://apify.com/v0iddo/kariyer-scraper
- Price: $0.84 per 1,000 results, nothing per run

Scrape job listings from Kariyer.net, the largest job board in Turkey, by city, keyword or listing link.

Example input:

```json
{
  "locations": [
    "istanbul"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `workModel`, `employmentType`, `sector`, `age`, `dateStatus`, `sponsored`, `search`, `url`

## IrishJobs.ie and Jobs.ie Scraper: Ireland Jobs and Salaries

- Actor ID: `v0iddo/irishjobs-scraper`
- Store page: https://apify.com/v0iddo/irishjobs-scraper
- Price: $1.23 per 1,000 results, nothing per run

Scrape job postings from IrishJobs.ie and Jobs.ie in Ireland: title, company, town, county, salary in EUR with min, max and period, date posted, closing date and snippet; with details, contract, work mode, province, map point and full text.

Example input:

```json
{
  "keywords": [
    "accountant"
  ],
  "location": "Dublin",
  "site": "irishjobs.ie",
  "includeDetails": false,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `county`, `salaryText`, `salaryMin`, `salaryMax`, `salaryInterval`, `datePosted`, `site`, `url`

## IIMJobs Scraper: India Finance and MBA Jobs

- Actor ID: `v0iddo/iimjobs-scraper`
- Store page: https://apify.com/v0iddo/iimjobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

iimjobs scraper for India finance, sales, consulting, HR and operations jobs from iimjobs.com: company, locations, experience, salary in lakhs when shown, skills, category, posting time, the employer's AmbitionBox rating and profile, and the description.

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

## Pracuj.pl Scraper: Poland Jobs, Salaries, Contract Type

- Actor ID: `v0iddo/pracuj-pl-scraper`
- Store page: https://apify.com/v0iddo/pracuj-pl-scraper
- Price: $0.95 + $0.004/start per 1,000 results

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

## Instahyre Jobs Scraper: India Jobs, Skills

- Actor ID: `v0iddo/instahyre-jobs-scraper`
- Store page: https://apify.com/v0iddo/instahyre-jobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Instahyre jobs scraper for India: title, company, locations, skills, experience in years, posting date, employment type, the description, and the employer's size, founding year, tagline and website.

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

Output fields: `title`, `company`, `advertiser`, `location`, `salaryText`, `salaryMin`, `salaryMax`, `salaryPeriod`, `salaryCurrency`, `jobType`, `workingOption`, `postedAt`, `expiresAt`, `url`

## Hirist Jobs Scraper: India Tech Jobs, Salary

- Actor ID: `v0iddo/hirist-jobs-scraper`
- Store page: https://apify.com/v0iddo/hirist-jobs-scraper
- Price: $0.50 per 1,000 results, nothing per run

Hirist jobs scraper for India tech jobs from hirist.tech: title, company, locations, experience in years, salary in lakhs when shown, skills, category, remote flag, posting time, the employer's AmbitionBox rating and profile, and the description.

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

## ATS Jobs Scraper: Greenhouse, Lever, Workday, Ashby

- Actor ID: `v0iddo/ats-jobs-scraper`
- Store page: https://apify.com/v0iddo/ats-jobs-scraper
- Price: $0.42 per 1,000 results, nothing per run

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

## Rozee.pk Jobs Scraper

- Actor ID: `v0iddo/rozeepk-jobs-scraper`
- Store page: https://apify.com/v0iddo/rozeepk-jobs-scraper
- Price: $0.79 per 1,000 results, nothing per run

Scrape job listings from Rozee.pk by keyword and optional city.

Example input:

```json
{
  "keywords": [
    "developer"
  ],
  "city": "",
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `jobId`, `title`, `company`, `city`, `jobType`, `experience`, `salaryMin`, `salaryMax`, `currency`, `skills`, `postedDate`, `applyBy`, `url`

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

## Handshake Jobs Scraper

- Actor ID: `v0iddo/handshake-jobs`
- Store page: https://apify.com/v0iddo/handshake-jobs
- Price: $0.85 per 1,000 results, nothing per run

Scrape open job postings from joinhandshake.com into structured rows: title, department, employment type, location, workplace type, compensation, published date, description, and application link.

Example input:

```json
{
  "keyword": "",
  "employmentType": "",
  "workplaceType": "",
  "maxItems": 20
}
```

Output fields: `jobId`, `title`, `department`, `employmentType`, `workplaceType`, `location`, `isRemote`, `publishedAt`, `compensationSummary`, `compensationMin`, `compensationMax`, `compensationCurrency`, `description`, `url`, `applyUrl`

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

## Pracuj.pl Salary Benchmark by Job Title and City

- Actor ID: `v0iddo/pracuj-pl-salary-benchmark`
- Store page: https://apify.com/v0iddo/pracuj-pl-salary-benchmark
- Price: $490.00 per 1,000 results, nothing per run

Get a salary benchmark for any job title from pracuj.pl postings in Poland: gross monthly median, quartiles and range in PLN, share of postings showing pay, listings, direct employers and agencies, top employers, work modes and contract types.

Example input:

```json
{
  "jobTitles": [
    "księgowa"
  ],
  "location": "Warszawa",
  "listingsPerBenchmark": 100,
  "detailPages": 10,
  "maxItems": 20
}
```

Output fields: `jobTitle`, `location`, `listingsOnSite`, `salariesUsed`, `salaryMin`, `salaryMedian`, `salaryMax`, `salarySharePercent`, `directEmployerPercent`, `searchUrl`

## Computrabajo Salary Benchmark by Job Title and Country

- Actor ID: `v0iddo/computrabajo-salary-benchmark`
- Store page: https://apify.com/v0iddo/computrabajo-salary-benchmark
- Price: $490.00 per 1,000 results, nothing per run

Get a salary benchmark for any job title from Computrabajo postings in 18 Latin American countries: monthly median, quartiles and range in local currency, share of postings showing pay, listings, top employers, cities, work modes and contract types.

Example input:

```json
{
  "jobTitles": [
    "contador"
  ],
  "countries": [
    "mx"
  ],
  "location": "Monterrey",
  "listingsPerBenchmark": 100,
  "detailPages": 10,
  "maxItems": 20
}
```

Output fields: `jobTitle`, `country`, `location`, `listingsOnSite`, `salariesUsed`, `salaryP25`, `salaryMedian`, `salaryP75`, `currency`, `salarySharePercent`, `searchUrl`

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

Output fields: `ats`, `company`, `title`, `location`, `country`, `remote`, `workplaceType`, `employmentType`, `postedAt`, `salaryMin`, `salaryMax`, `salaryCurrency`, `url`

## Computrabajo Job Alerts: New Jobs to Slack or Webhook

- Actor ID: `v0iddo/computrabajo-job-alerts`
- Store page: https://apify.com/v0iddo/computrabajo-job-alerts
- Price: $2.00 per 1,000 results, nothing per run

For recruiters and HR analysts: only new, changed or expired Computrabajo job offers in 18 LATAM countries, sent to Slack, Telegram or a webhook each run.

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

Output fields: `changeType`, `title`, `company`, `city`, `country`, `salaryText`, `workMode`, `changedFields`, `firstSeenAt`, `url`

## Computrabajo Scraper: LATAM Jobs and Salaries

- Actor ID: `v0iddo/computrabajo-scraper`
- Store page: https://apify.com/v0iddo/computrabajo-scraper
- Price: $1.39 + $0.000/start per 1,000 results

Computrabajo scraper for jobs in 18 Latin American countries: title, company with rating, city, region, salary with currency and period, contract, schedule, remote or hybrid, education, experience, skills, industry and dates.

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

## Pracuj.pl Job Alerts: New Offers to Slack, Telegram, Webhook

- Actor ID: `v0iddo/pracuj-pl-job-alerts`
- Store page: https://apify.com/v0iddo/pracuj-pl-job-alerts
- Price: $2.00 per 1,000 results, nothing per run

Watch pracuj.pl searches and get only new, changed or expired job offers, with salary and link, in one alert per run to Slack, Telegram or a webhook.

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

Output fields: `changeType`, `title`, `company`, `location`, `salaryText`, `workModes`, `changedFields`, `firstSeenAt`, `url`

## Freelancer.com Jobs and Projects Scraper

- Actor ID: `v0iddo/freelancer-jobs-projects-scraper`
- Store page: https://apify.com/v0iddo/freelancer-jobs-projects-scraper
- Price: $0.09 per 1,000 results, nothing per run

Scrape Freelancer.com job listings by skill: project title, description, average bid and whether it is hourly, bid count, required skills, payment verification status, and project URL.

Example input:

```json
{
  "skills": [
    "python"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `title`, `description`, `avgBid`, `hourly`, `currency`, `bidCount`, `skills`, `paymentVerified`, `daysLeft`, `url`

## No Fluff Jobs Scraper: Polish IT Jobs and Salaries

- Actor ID: `v0iddo/nofluffjobs`
- Store page: https://apify.com/v0iddo/nofluffjobs
- Price: $0.75 per 1,000 results, nothing per run

Scrape IT job offers from No Fluff Jobs (nofluffjobs.com) in Poland: title, company, category, seniority, must have skills, work mode, city, salary from and to with currency and period, B2B or employment contract, date and link.

Example input:

```json
{
  "technologies": [
    "Python"
  ],
  "salaryOnly": true,
  "maxItems": 20
}
```

Output fields: `title`, `companyName`, `category`, `seniority`, `workMode`, `city`, `skills`, `salaryFrom`, `salaryTo`, `currency`, `salaryInterval`, `salaryType`, `contractType`, `postedAt`, `url`

## We Work Remotely Jobs Scraper

- Actor ID: `v0iddo/weworkremotely-jobs-scraper`
- Store page: https://apify.com/v0iddo/weworkremotely-jobs-scraper
- Price: $0.85 per 1,000 results, nothing per run

Scrape remote job listings from weworkremotely.com by category or keyword.

Example input:

```json
{
  "categoryUrls": [
    "https://weworkremotely.com/categories/remote-devops-sysadmin-jobs",
    "https://weworkremotely.com/categories/remote-customer-support-jobs"
  ],
  "maxItems": 20
}
```

Output fields: `jobId`, `title`, `company`, `category`, `jobType`, `region`, `salary`, `postedDate`, `url`
