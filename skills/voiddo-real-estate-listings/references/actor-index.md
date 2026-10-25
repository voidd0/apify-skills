# Real estate listings for sale and rent: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Zillow Search Scraper: Homes for Sale, Rent and Sold

- Actor ID: `v0iddo/zillow-scraper`
- Store page: https://apify.com/v0iddo/zillow-scraper
- Price: $1.50 per 1,000 results, nothing per run

Scrape Zillow search results for homes for sale, rentals and recently sold properties: price, address, beds, baths, living area, lot size, home type, days on Zillow, coordinates and listing brokerage.

Example input:

```json
{
  "locations": [
    "Austin, TX"
  ],
  "listingType": "for_sale",
  "maxItems": 20
}
```

Output fields: `address`, `priceText`, `beds`, `baths`, `livingArea`, `homeType`, `status`, `daysOnZillow`, `brokerName`, `url`

## Fotocasa Scraper: Spain Homes for Sale and Rent

- Actor ID: `v0iddo/fotocasa-scraper`
- Store page: https://apify.com/v0iddo/fotocasa-scraper
- Price: $1.50 per 1,000 results, nothing per run

Scrape Fotocasa property listings for sale or to rent across Spain: price, price drop, rooms, bathrooms, surface, floor, features, neighbourhood and city, coordinates, photos, agency and publication date.

Example input:

```json
{
  "searchUrls": [
    "https://www.fotocasa.es/es/comprar/viviendas/madrid-capital/todas-las-zonas/l"
  ],
  "channel": "buy",
  "maxItems": 20
}
```

Output fields: `propertyId`, `address`, `price`, `rentPeriod`, `propertyType`, `rooms`, `bathrooms`, `surfaceM2`, `sellerType`, `agency`, `publishedAt`, `url`

## Rightmove Scraper: UK Property for Sale and to Rent

- Actor ID: `v0iddo/rightmove-scraper`
- Store page: https://apify.com/v0iddo/rightmove-scraper
- Price: $1.50 per 1,000 results, nothing per run

Scrape Rightmove property listings for sale or to rent across the UK: price, address, bedrooms, bathrooms, property type, estate agent branch, added or reduced date, coordinates, photo and link.

Example input:

```json
{
  "searchUrls": [
    "https://www.rightmove.co.uk/property-for-sale/find.html?locationIdentifier=REGION%5E904"
  ],
  "channel": "buy",
  "maxItems": 20
}
```

Output fields: `propertyId`, `displayAddress`, `priceText`, `bedrooms`, `bathrooms`, `propertyType`, `propertySubType`, `agent`, `addedOrReduced`, `image`, `url`
