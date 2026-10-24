---
name: voiddo-events
description: "Find public events on Eventbrite by query and location: name, start and end time, venue, city, online flag and link. Routes to 1 pay-per-result Apify Actors by vøiddo. Use when the user asks to find events in a city, list conferences on a topic, build an events calendar, monitor new events."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "events, eventbrite, conferences, meetups, event-calendar"
---

# Events by place and topic

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Find public events on Eventbrite by query and location: name, start and end time, venue, city, online flag and link.

## Example prompts

Prompts this skill handles:

- "List tech meetups in London next month."
- "Find online marketing webinars this week."

Out of scope (the boundary): Buying tickets: out of scope.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/eventbrite-events-search" --input --json --user-agent voiddo-skills/voiddo-events 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/eventbrite-events-search" -i '{"queries": ["tech-conference", "design-workshop", "startup-pitch"], "maxEventsPerQuery": 20}' --json --user-agent voiddo-skills/voiddo-events 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Search Eventbrite events by keyword and location. | `v0iddo/eventbrite-events-search` | $0.30 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/eventbrite-events-search`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~eventbrite-events-search/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"queries": ["tech-conference", "design-workshop", "startup-pitch"], "maxEventsPerQuery": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
