---
name: voiddo-job-postings
description: "Collect open job postings from company careers pages (Greenhouse, Lever, Ashby, Workday, Workable and more) and national job boards into one table: title, company, location, remote flag, posting date, salary where the employer publishes it, and the link. Routes to 16 pay-per-result Apify Actors by vøiddo. Use when the user asks to find jobs, scrape job postings, export a company's careers page, monitor new roles, collect salary data, build a job board feed, track hiring at competitors."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "jobs, job-postings, careers-page, greenhouse, lever, ashby, workday, workable, ats, salary-data, recruiting"
---

# Job postings from careers pages and job boards

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Collect open job postings from company careers pages (Greenhouse, Lever, Ashby, Workday, Workable and more) and national job boards into one table: title, company, location, remote flag, posting date, salary where the employer publishes it, and the link.

## Example prompts

Prompts this skill handles:

- "Export every open job at Spotify, Notion and Discord to a CSV with location and remote flag."
- "Which engineering roles did NVIDIA post on its Workday site in the last 7 days?"
- "Give me remote data engineer jobs from these careers pages, only the new ones since yesterday."

Out of scope (the boundary): LinkedIn Jobs or Google Jobs: this skill does not cover them.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/indeed-scraper" --input --json --user-agent voiddo-skills/voiddo-job-postings 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/indeed-scraper" -i '{"query": "data analyst", "location": "Remote", "datePosted": "any", "jobType": "", "maxPages": 1, "maxItems": 20}' --json --user-agent voiddo-skills/voiddo-job-postings 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Scrape Indeed.com job search results: title, company and its rating, location, remote or hybrid, salary ran... | `v0iddo/indeed-scraper` | $0.50 |
| Scrape startup jobs from Wellfound (AngelList Talent) by role and location, remote jobs or any search page:... | `v0iddo/wellfound-jobs-scraper` | $0.50 |
| Scrape remote jobs from Remote OK, We Work Remotely, Jobicy, Working Nomads and Arbeitnow in one feed: titl... | `v0iddo/remote-jobs-scraper` | $0.50 |
| Scrape India jobs from Instahyre: title, company, locations, skills, experience in years, posting date, emp... | `v0iddo/instahyre-jobs-scraper` | $0.50 |
| Collect every open job from any Workday careers site (myworkdayjobs.com): title, location, country, remote... | `v0iddo/workday-jobs-scraper` | $0.90 |
| Scrape UK job postings from reed.co.uk: title, company, agency or employer, place, county, region, postcode... | `v0iddo/reed-jobs-scraper` | $0.45 |
| Scrape India tech jobs from hirist.tech: title, company, locations, experience in years, salary in lakhs wh... | `v0iddo/hirist-jobs-scraper` | $0.50 |
| Scrape India finance, sales, consulting, HR and operations jobs from iimjobs.com: company, locations, exper... | `v0iddo/iimjobs-scraper` | $0.50 |
| Scrape Swiss job postings from jobs.ch and jobup.ch: title, company, address, canton, workload percent, emp... | `v0iddo/jobs-ch-scraper` | $0.90 |
| Scrape job postings from Computrabajo in 18 Latin American countries: title, company with rating, city, reg... | `v0iddo/computrabajo-scraper` | $0.50 |
| Collect public job postings from Greenhouse, Lever, Workday, Workable, Ashby, Recruitee, Personio and Bambo... | `v0iddo/ats-jobs-scraper` | $1.20 |
| Scrape Brazilian job postings from Gupy, the hiring system of most large employers in Brazil: title, compan... | `v0iddo/gupy-scraper` | $0.50 |
| Scrape Polish job postings from pracuj.pl: title, company, workplaces and address, salary per contract type... | `v0iddo/pracuj-pl-scraper` | $0.50 |
| Ashby jobs API and scraper. | `v0iddo/ashby-public-jobs` | $1.70 |
| Greenhouse jobs API and scraper. | `v0iddo/greenhouse-public-jobs` | $0.20 |
| Lever jobs API and scraper. | `v0iddo/lever-public-jobs` | $0.20 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/indeed-scraper,v0iddo/wellfound-jobs-scraper,v0iddo/remote-jobs-scraper,v0iddo/instahyre-jobs-scraper,v0iddo/workday-jobs-scraper,v0iddo/reed-jobs-scraper,v0iddo/hirist-jobs-scraper,v0iddo/iimjobs-scraper,v0iddo/jobs-ch-scraper,v0iddo/computrabajo-scraper`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~indeed-scraper/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"query": "data analyst", "location": "Remote", "datePosted": "any", "jobType": "", "maxPages": 1, "maxItems": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
