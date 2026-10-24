# Products, prices and sales signals from marketplaces: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Shopify Scraper: Products, Prices, Stock

- Actor ID: `v0iddo/shopify-store-intelligence`
- Store page: https://apify.com/v0iddo/shopify-store-intelligence
- Price: $0.50 per 1,000 results, nothing per run

Scrape products from any Shopify store: prices, compare-at price and discount, stock per variant, SKU, barcode, options, images, tags and the store's currency.

Example input:

```json
{
  "stores": [
    "gymshark.com",
    "allbirds.com",
    "kith.com"
  ],
  "maxProductsPerStore": 20
}
```

Output fields: `storeDomain`, `title`, `url`, `vendor`, `productType`, `minPrice`, `maxPrice`, `currency`, `discountPercent`, `available`, `variantsInStock`, `updatedAt`
