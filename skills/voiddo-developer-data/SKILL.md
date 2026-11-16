---
name: voiddo-developer-data
description: "Track the developer ecosystem: npm and PyPI package metadata and releases, GitHub trending repositories, GitHub security advisories, NVD CVE records, Hacker News search and Product Hunt launches. Routes to 5 pay-per-result Apify Actors by vøiddo. Use when the user asks to find trending repos, watch package releases, check a dependency for vulnerabilities, follow new CVEs, search Hacker News, see today's Product Hunt launches."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "npm, pypi, github-trending, security-advisories, cve, nvd, hacker-news, product-hunt, developer-tools"
---

# Packages, repositories and vulnerabilities

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Track the developer ecosystem: npm and PyPI package metadata and releases, GitHub trending repositories, GitHub security advisories, NVD CVE records, Hacker News search and Product Hunt launches.

## Example prompts

Prompts this skill handles:

- "Which Python repositories are trending on GitHub this week?"
- "List new critical CVEs for nginx published in the last 7 days."
- "Get the latest versions and release dates of these 30 npm packages."

Out of scope (the boundary): Scanning private code: out of scope.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/hn-algolia-search" --input --json --user-agent voiddo-skills/voiddo-developer-data 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/hn-algolia-search" -i '{"queries": ["Show HN: open source"], "maxResultsPerQuery": 20}' --json --user-agent voiddo-skills/voiddo-developer-data 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Search Hacker News via the public Algolia API. | `v0iddo/hn-algolia-search` | $0.10 |
| Snapshot PyPI package metadata using the public pypi.org/pypi/<pkg>/json endpoint. | `v0iddo/pypi-package-tracker` | $0.20 |
| For each ecosystem (NPM, PIP, MAVEN, NUGET, RUBYGEMS, RUST, GO, ACTIONS, SWIFT and more), pull recent GitHu... | `v0iddo/github-security-advisories` | $0.50 |
| Snapshot npm package stats from the public registry and downloads APIs. | `v0iddo/npm-package-tracker` | $0.20 |
| Pull new/modified CVEs from NIST NVD. | `v0iddo/nvd-cve-tracker` | $2.00 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/hn-algolia-search,v0iddo/pypi-package-tracker,v0iddo/github-security-advisories,v0iddo/npm-package-tracker,v0iddo/nvd-cve-tracker`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~hn-algolia-search/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"queries": ["Show HN: open source"], "maxResultsPerQuery": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
