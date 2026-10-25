# Products, prices and sales signals from marketplaces: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Amazon Product Scraper: ASIN Details, Price, Sales Rank

- Actor ID: `v0iddo/amazon-product-scraper`
- Store page: https://apify.com/v0iddo/amazon-product-scraper
- Price: $1.50 per 1,000 results, nothing per run

Scrape Amazon.com product pages from ASINs or links: title, brand, price, list price, rating, ratings count, stock status, features, description, images, categories, best sellers rank, variations and product details.

Example input:

```json
{
  "products": [
    "B09B8V1LZ3",
    "0735211299",
    "B00FLYWNYQ",
    "B09HM94VDS",
    "B0CFPJYX7P",
    "B0BP9SNVH9"
  ],
  "maxItems": 20
}
```

Output fields: `asin`, `title`, `brand`, `price`, `listPrice`, `rating`, `ratingsCount`, `inStock`, `mainImage`, `url`

## Amazon Search Scraper: Monthly Sales, Badges, Prices

- Actor ID: `v0iddo/amazon-search-scraper`
- Store page: https://apify.com/v0iddo/amazon-search-scraper
- Price: $1.20 per 1,000 results, nothing per run

Scrape Amazon.com search results into clean product rows: ASIN, title, price, list price, star rating, ratings count, monthly sales badge, Best Seller and Overall Pick badges, sponsored flag, image and link.

Example input:

```json
{
  "searchTerms": [
    "wireless earbuds"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `asin`, `title`, `price`, `rating`, `ratingsCount`, `badge`, `sponsored`, `url`

## AliExpress Scraper: Prices, Sold Counts

- Actor ID: `v0iddo/aliexpress-scraper`
- Store page: https://apify.com/v0iddo/aliexpress-scraper
- Price: $1.50 per 1,000 results, nothing per run

Scrape AliExpress search results into product rows: product ID, title, sale price, original price, discount, star rating, units sold, Choice and shipping flags, delivery estimate, image and link.

Example input:

```json
{
  "searchTerms": [
    "wireless earbuds"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `productId`, `title`, `price`, `originalPrice`, `rating`, `sold`, `choice`, `url`

## Amazon Bestsellers Scraper: New Releases

- Actor ID: `v0iddo/amazon-bestsellers-scraper`
- Store page: https://apify.com/v0iddo/amazon-bestsellers-scraper
- Price: $1.00 per 1,000 results, nothing per run

Scrape Amazon.com Best Sellers and New Releases lists by category link: rank, ASIN, title, price, star rating, ratings count, image and product link.

Example input:

```json
{
  "categoryUrls": [
    "https://www.amazon.com/gp/bestsellers/electronics"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `rank`, `asin`, `title`, `price`, `rating`, `ratingsCount`, `category`, `listType`, `image`, `url`

## eBay Scraper: Category Listings, Prices, Sold and Watchers

- Actor ID: `v0iddo/ebay-scraper`
- Store page: https://apify.com/v0iddo/ebay-scraper
- Price: $2.00 per 1,000 results, nothing per run

Collect listings from eBay category pages: title, price with currency, condition, shipping, sold and watcher counts, bids when shown, photo and link.

Example input:

```json
{
  "categoryUrls": [
    "https://www.ebay.com/b/Cell-Phones-Smartphones/9355/bn_320094"
  ],
  "maxItems": 20
}
```

Output fields: `title`, `price`, `currency`, `priceText`, `previousPrice`, `condition`, `brand`, `shippingText`, `soldText`, `watchersText`, `image`, `url`

## TikTok Shop Scraper: Products, Units Sold

- Actor ID: `v0iddo/tiktok-shop-product-scraper`
- Store page: https://apify.com/v0iddo/tiktok-shop-product-scraper
- Price: $4.25 per 1,000 results, nothing per run

Scrape TikTok Shop product pages in the United States from product links or IDs: title, price, original price, discount, units sold, rating, review count, stock, variants, images, category, shipping and shop details.

Example input:

```json
{
  "products": [
    "https://shop.tiktok.com/us/pdp/cat-nail-clipper-by-potaroma-adjustable-sizes-built-in-file-safe-for-kittens-cats/1731578642912612516",
    "https://shop.tiktok.com/us/pdp/zila-cropped-cable-knit-top-100-cotton-front-button-closures/1732500518270439586",
    "https://shop.tiktok.com/us/pdp/jetech-matte-case-for-iphone-16-shockproof-anti-fingerprint/1732347639758557964",
    "https://shop.tiktok.com/us/pdp/jetech-screen-protector-for-ipad-a16-9h-tempered-glass-2-pack/1732359237559685900",
    "https://shop.tiktok.com/us/pdp/waterproof-mascara-by-sace-lady/1730219123026333900",
    "https://shop.tiktok.com/us/pdp/deodorant-truly-beauty-unicorn-fruit-cotton-candy-scent-for-bright-skin/1729430515554816714",
    "https://shop.tiktok.com/us/pdp/womens-bucket-hat-by-unknown-colorblock-knit-warm-fisherman-style/1729721254514234223",
    "https://shop.tiktok.com/us/pdp/ashwagandha-gummies-by-goli-ksm-66-mixed-berry-vegan-non-gmo/1729527313880355335",
    "https://shop.tiktok.com/us/pdp/eskute-v101-1500w-electric-bike-28mph-85mi-range-7-speed/1729506602529690818",
    "https://shop.tiktok.com/us/pdp/centella-green-tea-hydrating-gel-cleanser-gentle-daily-use/1729449803340812401"
  ],
  "maxItems": 20
}
```

Output fields: `productId`, `title`, `price`, `originalPrice`, `currency`, `soldCount`, `rating`, `reviewCount`, `shopName`, `status`, `mainImage`, `url`

## Vinted Search Scraper: Listings, Prices, Brands, Sizes

- Actor ID: `v0iddo/vinted-scraper`
- Store page: https://apify.com/v0iddo/vinted-scraper
- Price: $1.50 per 1,000 results, nothing per run

Collect public Vinted listings by search word or catalog link: title, brand, size, condition, price with currency, total with the buyer fee, favourites, photo and link.

Example input:

```json
{
  "searchTerms": [
    "nike"
  ],
  "maxItems": 20
}
```

Output fields: `title`, `brand`, `size`, `condition`, `price`, `currency`, `totalPrice`, `favourites`, `photo`, `url`

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
