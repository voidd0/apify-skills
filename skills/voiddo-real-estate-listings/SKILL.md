---
name: voiddo-real-estate-listings
description: "Collect property listings for sale, rent and recently sold from Zillow (US), Rightmove (UK) and Fotocasa (Spain): price, address, beds, baths, area, listing date, agency and link. Routes to 3 pay-per-result Apify Actors by vøiddo. Use when the user asks to find homes for sale in a city, track rents, compare listing prices, research a housing market, export listings to a spreadsheet."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "real-estate, property-listings, zillow, rightmove, fotocasa, rentals, housing-market, home-prices"
---

# Real estate listings for sale and rent

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Collect property listings for sale, rent and recently sold from Zillow (US), Rightmove (UK) and Fotocasa (Spain): price, address, beds, baths, area, listing date, agency and link.

## Example prompts

Prompts this skill handles:

- "Get homes for sale in Austin, TX under $500k with beds, baths and price per square foot."
- "Export Rightmove rentals in Manchester to CSV."
- "Which Fotocasa flats in Barcelona dropped their price this week?"

Out of scope (the boundary): Owner phone numbers or agent contact details: never collected.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/fotocasa-scraper" --input --json --user-agent voiddo-skills/voiddo-real-estate-listings 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/fotocasa-scraper" -i '{"searchUrls": ["https://www.fotocasa.es/es/comprar/viviendas/madrid-capital/todas-las-zonas/l"], "channel": "buy", "maxItems": 20}' --json --user-agent voiddo-skills/voiddo-real-estate-listings 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Scrape Fotocasa property listings for sale or to rent across Spain: price, price drop, rooms, bathrooms, su... | `v0iddo/fotocasa-scraper` | $1.50 |
| Scrape Rightmove property listings for sale or to rent across the UK: price, address, bedrooms, bathrooms,... | `v0iddo/rightmove-scraper` | $1.50 |
| Scrape Zillow search results for homes for sale, rentals and recently sold properties: price, address, beds... | `v0iddo/zillow-scraper` | $1.50 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/fotocasa-scraper,v0iddo/rightmove-scraper,v0iddo/zillow-scraper`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~fotocasa-scraper/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"searchUrls": ["https://www.fotocasa.es/es/comprar/viviendas/madrid-capital/todas-las-zonas/l"], "channel": "buy", "maxItems": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
