---
name: voiddo-market-data
description: "Get market data: Yahoo Finance quotes and key statistics, currency exchange rates, CoinGecko tokens by category and DefiLlama protocol snapshots (TVL, chains, category). Routes to 5 pay-per-result Apify Actors by vøiddo. Use when the user asks to get stock quotes, build a watchlist table, convert currencies at today's rate, list tokens in a crypto category, compare DeFi protocols by TVL."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "stock-quotes, yahoo-finance, exchange-rates, currency, crypto, coingecko, defillama, tvl"
---

# Stock quotes, exchange rates and crypto market data

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Get market data: Yahoo Finance quotes and key statistics, currency exchange rates, CoinGecko tokens by category and DefiLlama protocol snapshots (TVL, chains, category).

## Example prompts

Prompts this skill handles:

- "Quote AAPL, MSFT and NVDA with market cap and P/E."
- "Convert 10,000 USD to EUR, GBP and JPY at today's rates."
- "List the 50 largest DeFi protocols by TVL with their chains."

Out of scope (the boundary): Trading or investment advice: out of scope.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/coingecko-category-snapshot" --input --json --user-agent voiddo-skills/voiddo-market-data 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/coingecko-category-snapshot" -i '{"categories": ["layer-1", "meme-token"], "maxCoinsPerCategory": 20}' --json --user-agent voiddo-skills/voiddo-market-data 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| For each CoinGecko category ID (`layer-1`, `defi`, `meme-token`, etc.), pull its coins by market cap: 250 p... | `v0iddo/coingecko-category-snapshot` | $0.10 |
| Pulls the top 100 tokens by market cap in each CoinGecko category (DeFi, meme, L1, ecosystem tags) with cur... | `v0iddo/coingecko-tokens-by-category` | $1.00 |
| Snapshot every DefiLlama-tracked protocol filtered by chain, category, and TVL range. | `v0iddo/defillama-protocols-snapshot` | $0.10 |
| Latest and historical euro foreign exchange reference rates from the European Central Bank, with conversion... | `v0iddo/currency-exchange-rates` | $3.40 |
| Scrape Yahoo Finance quotes and key statistics for stocks, ETFs, indexes, crypto, currencies and futures: p... | `v0iddo/yahoo-finance-scraper` | $1.00 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/coingecko-category-snapshot,v0iddo/coingecko-tokens-by-category,v0iddo/defillama-protocols-snapshot,v0iddo/currency-exchange-rates,v0iddo/yahoo-finance-scraper`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~coingecko-category-snapshot/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"categories": ["layer-1", "meme-token"], "maxCoinsPerCategory": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
