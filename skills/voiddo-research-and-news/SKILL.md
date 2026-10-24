---
name: voiddo-research-and-news
description: "Collect research and media: PubMed citations, Crossref publications, news articles as clean text, Substack and Medium posts, and podcast search results. Routes to 6 pay-per-result Apify Actors by vøiddo. Use when the user asks to monitor new papers on a topic, collect news articles as text, archive a newsletter, find podcasts about a subject."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "pubmed, crossref, research-papers, news-articles, substack, medium, podcasts, article-extraction"
---

# Papers, articles, newsletters and podcasts

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Collect research and media: PubMed citations, Crossref publications, news articles as clean text, Substack and Medium posts, and podcast search results.

## Example prompts

Prompts this skill handles:

- "Get this week's PubMed papers on GLP-1 with title, journal and DOI."
- "Extract the full text of these 40 news article links."
- "Export every post of this Substack newsletter with dates."

Out of scope (the boundary): Paywalled articles: the Actors read public pages only.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/medium-rss-tracker" --input --json --user-agent voiddo-skills/voiddo-research-and-news 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/medium-rss-tracker" -i '{"feeds": ["@medium", "tag/programming", "tag/data-science"], "maxArticlesPerFeed": 20}' --json --user-agent voiddo-skills/voiddo-research-and-news 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Pull Medium articles via the public RSS feed endpoints: /feed/@user, /feed/tag/{tag}, /feed/{publication-sl... | `v0iddo/medium-rss-tracker` | $0.20 |
| Substack scraper for newsletter posts. | `v0iddo/substack-newsletter-posts` | $1.06 |
| Pull daily-new PubMed citations matching any query. | `v0iddo/pubmed-daily-citations-tracker` | $1.00 |
| For each query, pull recent works from Crossref's public REST API with a server-side date filter. | `v0iddo/crossref-recent-publications` | $0.20 |
| Extract news articles from any publisher. | `v0iddo/news-scraper` | $1.50 |
| Collect the posts of any Substack publication: title, subtitle, date, link, paywall flag, reactions, commen... | `v0iddo/substack-scraper` | $1.00 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/medium-rss-tracker,v0iddo/substack-newsletter-posts,v0iddo/pubmed-daily-citations-tracker,v0iddo/crossref-recent-publications,v0iddo/news-scraper,v0iddo/substack-scraper`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~medium-rss-tracker/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"feeds": ["@medium", "tag/programming", "tag/data-science"], "maxArticlesPerFeed": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
