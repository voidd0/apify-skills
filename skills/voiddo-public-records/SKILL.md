---
name: voiddo-public-records
description: "Query official public records: SEC filings (Form 4 insider trades, 13F holdings, 13D/13G, 8-K events), the OFAC sanctions list, USAspending federal awards, the Federal Register, FCC notices, NIH grants, openFDA recalls and ClinicalTrials.gov. Routes to 10 pay-per-result Apify Actors by vøiddo. Use when the user asks to screen a name against sanctions, track insider buying, follow institutional holdings, find federal contracts or grants, monitor new regulations, check drug recalls, look up UK companies."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "sec-filings, insider-trading, 13f, ofac, sanctions-screening, usaspending, federal-register, fda, grants, companies-house"
---

# Government and regulatory records

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Query official public records: SEC filings (Form 4 insider trades, 13F holdings, 13D/13G, 8-K events), the OFAC sanctions list, USAspending federal awards, the Federal Register, FCC notices, NIH grants, openFDA recalls and ClinicalTrials.gov.

## Example prompts

Prompts this skill handles:

- "Screen these 200 company names against the OFAC SDN list."
- "Which insiders bought shares of Apple in the last 30 days?"
- "List federal contracts over $1M awarded to Palantir this year."

Out of scope (the boundary): Legal advice or a compliance verdict: the skill returns the records, a person decides.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/clinicaltrials-updates-tracker" --input --json --user-agent voiddo-skills/voiddo-public-records 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/clinicaltrials-updates-tracker" -i '{"queries": ["lung cancer"], "maxResultsPerQuery": 20}' --json --user-agent voiddo-skills/voiddo-public-records 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Pull recently-updated ClinicalTrials.gov studies matching a query. | `v0iddo/clinicaltrials-updates-tracker` | $2.98 |
| Pull recent federal contract and grant awards from USAspending.gov. | `v0iddo/usaspending-federal-awards` | $1.70 |
| Pull Federal Register articles filtered by agency, document type, date range, significant-rule flag, or ful... | `v0iddo/federal-register-tracker` | $0.10 |
| Pull recent NIH research grants from RePORTER. | `v0iddo/nih-reporter-grants` | $3.00 |
| Pull recent SEC 8-K filings (Current Reports) by stock ticker. | `v0iddo/sec-8k-material-events-tracker` | $10.00 |
| Pull recent FDA drug recall actions. | `v0iddo/openfda-drug-recalls` | $5.00 |
| Pull clean, parsed Form 4 insider trades from SEC EDGAR by ticker. | `v0iddo/sec-form4-insider-trades` | $2.32 |
| Pull SEC Form 13F quarterly holdings for any institutional manager by CIK. | `v0iddo/sec-13f-institutional-holdings` | $1.53 |
| Scrape SEC EDGAR 13D and 13G beneficial ownership filings by company CIK. | `v0iddo/sec-13d-13g-beneficial-ownership` | $4.89 |
| Scrapes FCC ECFS (Electronic Comment Filing System) filings and public notices by docket/proceeding number. | `v0iddo/fcc-public-notices` | $2.55 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/clinicaltrials-updates-tracker,v0iddo/usaspending-federal-awards,v0iddo/federal-register-tracker,v0iddo/nih-reporter-grants,v0iddo/sec-8k-material-events-tracker,v0iddo/openfda-drug-recalls,v0iddo/sec-form4-insider-trades,v0iddo/sec-13f-institutional-holdings,v0iddo/sec-13d-13g-beneficial-ownership,v0iddo/fcc-public-notices`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~clinicaltrials-updates-tracker/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"queries": ["lung cancer"], "maxResultsPerQuery": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
