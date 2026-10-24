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

## Eventbrite Event Data Scraper: City, Dates, Ticket Prices

- Actor ID: `v0iddo/mint-eventbrite-scraper`
- Store page: https://apify.com/v0iddo/mint-eventbrite-scraper
- Price: $1.00 per 1,000 results, nothing per run

Collect public Eventbrite events for any city or online: name, start and end, venue and city, online flag, ticket prices, organizer name, link and image.

Example input:

```json
{
  "locations": [
    "ny--new-york"
  ],
  "maxItems": 20
}
```

Output fields: `name`, `start`, `end`, `venueName`, `city`, `isOnline`, `isFree`, `priceMin`, `organizerName`, `url`, `image`
