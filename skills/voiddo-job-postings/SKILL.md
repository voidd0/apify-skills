---
name: voiddo-job-postings
description: "Collect open job postings from company careers pages (Greenhouse, Lever, Ashby, Workday, Workable and more) and national job boards into one table: title, company, location, remote flag, posting date, salary where the employer publishes it, and the link. Routes to 5 pay-per-result Apify Actors by vøiddo. Use when the user asks to find jobs, scrape job postings, export a company's careers page, monitor new roles, collect salary data, build a job board feed, track hiring at competitors."
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

       apify actors info "v0iddo/greenhouse-public-jobs" --input --json --user-agent voiddo-skills/voiddo-job-postings 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/greenhouse-public-jobs" -i '{"companies": ["stripe", "airbnb", "vercel"], "maxJobsPerCompany": 20}' --json --user-agent voiddo-skills/voiddo-job-postings 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Greenhouse jobs API and scraper. | `v0iddo/greenhouse-public-jobs` | $0.20 |
| Ashby jobs API and scraper. | `v0iddo/ashby-public-jobs` | $1.70 |
| Lever jobs API and scraper. | `v0iddo/lever-public-jobs` | $0.20 |
| Collect public job postings from Greenhouse, Lever, Workday, Workable, Ashby, Recruitee, Personio and Bambo... | `v0iddo/ats-jobs-scraper` | $1.20 |
| Collect every open job from any Workday careers site (myworkdayjobs.com): title, location, country, remote... | `v0iddo/workday-jobs-scraper` | $0.90 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/greenhouse-public-jobs,v0iddo/ashby-public-jobs,v0iddo/lever-public-jobs,v0iddo/ats-jobs-scraper,v0iddo/workday-jobs-scraper`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~greenhouse-public-jobs/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"companies": ["stripe", "airbnb", "vercel"], "maxJobsPerCompany": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
