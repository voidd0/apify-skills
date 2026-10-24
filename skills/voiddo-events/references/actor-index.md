# Events by place and topic: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Eventbrite Scraper: Events by Query and Location

- Actor ID: `v0iddo/eventbrite-events-search`
- Store page: https://apify.com/v0iddo/eventbrite-events-search
- Price: $0.30 per 1,000 results, nothing per run

Search Eventbrite events by keyword and location.

Example input:

```json
{
  "queries": [
    "tech-conference",
    "design-workshop",
    "startup-pitch"
  ],
  "maxEventsPerQuery": 20
}
```

Output fields: `id`, `title`, `organizer`, `startDate`, `endDate`, `isOnline`, `venueName`, `city`, `priceMin`, `priceMax`, `url`
