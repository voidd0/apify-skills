---
name: voiddo-app-store-data
description: "Read app and extension data from the Apple App Store, Google Play, Chrome Web Store, VS Code marketplace, JetBrains Marketplace and Steam: metadata, ratings, top charts, developer portfolios and reviews. Routes to 10 pay-per-result Apify Actors by vøiddo. Use when the user asks to research competitor apps, track app rankings, collect app reviews by country, list a developer's apps, find popular extensions or plugins."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "app-store, google-play, aso, app-reviews, top-charts, chrome-extensions, vscode, jetbrains, steam"
---

# App stores and extension marketplaces

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Read app and extension data from the Apple App Store, Google Play, Chrome Web Store, VS Code marketplace, JetBrains Marketplace and Steam: metadata, ratings, top charts, developer portfolios and reviews.

## Example prompts

Prompts this skill handles:

- "Show the top 50 iPhone apps in Germany today."
- "Get the latest App Store reviews of Duolingo in the US and the UK with stars."
- "List the most installed VS Code extensions for Python."

Out of scope (the boundary): Downloading app binaries: out of scope.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/app-store-app-metadata" --input --json --user-agent voiddo-skills/voiddo-app-store-data 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/app-store-app-metadata" -i '{"appIds": ["389801252", "6448311069"]}' --json --user-agent voiddo-skills/voiddo-app-store-data 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Snapshot Apple App Store app metadata via the public iTunes Lookup API. | `v0iddo/app-store-app-metadata` | $0.50 |
| Scrape Apple App Store reviews and ratings for any iOS app, storefront by storefront. | `v0iddo/app-store-reviews-tracker` | $0.30 |
| Snapshot Chrome Web Store extension metadata via the public listing page. | `v0iddo/chrome-webstore-extensions` | $0.50 |
| Search the Apple Podcasts catalog via the public iTunes Search API. | `v0iddo/itunes-podcast-search` | $0.20 |
| Search the Apple App Store by keyword and country. | `v0iddo/app-store-search` | $0.20 |
| Scrape Steam player reviews by App ID. | `v0iddo/steam-game-reviews` | $1.00 |
| Snapshot Android app metadata from Google Play for any package name, in any country. | `v0iddo/google-play-app-metadata` | $0.50 |
| Fetches extension metadata (downloads, version, publisher, repo, license, tags, timestamps) from the Open V... | `v0iddo/vscode-marketplace-extensions` | $1.00 |
| Pull every app under an Apple App Store developer identifier (artistId). | `v0iddo/itunes-developer-portfolio` | $2.38 |
| Scrape JetBrains Marketplace plugins by numeric ID: name, vendor, rating, downloads, description, link, pre... | `v0iddo/jetbrains-marketplace-plugins` | $1.00 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/app-store-app-metadata,v0iddo/app-store-reviews-tracker,v0iddo/chrome-webstore-extensions,v0iddo/itunes-podcast-search,v0iddo/app-store-search,v0iddo/steam-game-reviews,v0iddo/google-play-app-metadata,v0iddo/vscode-marketplace-extensions,v0iddo/itunes-developer-portfolio,v0iddo/jetbrains-marketplace-plugins`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~app-store-app-metadata/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"appIds": ["389801252", "6448311069"]}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
