# Products, prices and sales signals from marketplaces: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Amazon Product Details Scraper: ASIN, Price, Sales Rank

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
- Price: $0.51 per 1,000 results, nothing per run

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

## TikTok Shop Scraper: Products, Prices, Units Sold, Shops

- Actor ID: `v0iddo/tiktok-shop-product-scraper`
- Store page: https://apify.com/v0iddo/tiktok-shop-product-scraper
- Price: $2.29 per 1,000 results, nothing per run

Scrape TikTok Shop product pages in the United States from product links or IDs: title, price, original price, discount, units sold, rating, review count, stock, variants, images, category, shipping and shop details.

Example input:

```json
{
  "products": [
    "https://shop.tiktok.com/us/pdp/cat-nail-clipper-by-potaroma-adjustable-sizes-built-in-file-safe-for-kittens-cats/1731578642912612516",
    "https://shop.tiktok.com/us/pdp/zila-cropped-cable-knit-top-100-cotton-front-button-closures/1732500518270439586",
    "https://shop.tiktok.com/us/pdp/jetech-matte-case-for-iphone-16-shockproof-anti-fingerprint/1732347639758557964",
    "https://shop.tiktok.com/us/pdp/waterproof-mascara-by-sace-lady/1730219123026333900",
    "https://shop.tiktok.com/us/pdp/deodorant-truly-beauty-unicorn-fruit-cotton-candy-scent-for-bright-skin/1729430515554816714",
    "https://shop.tiktok.com/us/pdp/womens-bucket-hat-by-unknown-colorblock-knit-warm-fisherman-style/1729721254514234223",
    "https://shop.tiktok.com/us/pdp/ashwagandha-gummies-by-goli-ksm-66-mixed-berry-vegan-non-gmo/1729527313880355335",
    "https://shop.tiktok.com/us/pdp/eskute-v101-1500w-electric-bike-28mph-85mi-range-7-speed/1729506602529690818"
  ],
  "maxItems": 20
}
```

Output fields: `productId`, `title`, `price`, `originalPrice`, `currency`, `soldCount`, `rating`, `reviewCount`, `shopName`, `status`, `mainImage`, `url`

## Alibaba Scraper: Prices, MOQ, Verified Suppliers

- Actor ID: `v0iddo/alibaba-scraper`
- Store page: https://apify.com/v0iddo/alibaba-scraper
- Price: $0.75 per 1,000 results, nothing per run

Scrape Alibaba.com product offers by keyword: price range and quantity price tiers, minimum order, units sold, ratings, certifications, and the supplier's name, country, years, verified badge and response rate.

Example input:

```json
{
  "searchTerms": [
    "led strip lights"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `productId`, `title`, `priceMin`, `priceMax`, `minOrder`, `minOrderUnit`, `sold`, `supplierName`, `supplierCountry`, `url`

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

## Vinted Product Scraper: Search Listings, Prices, Brands, Sizes

- Actor ID: `v0iddo/vinted-scraper`
- Store page: https://apify.com/v0iddo/vinted-scraper
- Price: $0.85 per 1,000 results, nothing per run

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

## Alibaba Supplier Shortlist by Price, MOQ and Trust

- Actor ID: `v0iddo/alibaba-supplier-shortlist`
- Store page: https://apify.com/v0iddo/alibaba-supplier-shortlist
- Price: $490.00 per 1,000 results, nothing per run

Get a ranked shortlist of Alibaba.com suppliers for each product you name: each supplier scored on price against the market median, fit to your minimum order, Verified, Trade Assurance, years, rating and units sold, with its best offer and the reasons.

Example input:

```json
{
  "searchTerms": [
    "led strip lights"
  ],
  "targetPrice": 5,
  "targetMOQ": 50,
  "maxPages": 2,
  "shortlistSize": 10,
  "maxItems": 20
}
```

Output fields: `rank`, `score`, `supplierName`, `supplierCountry`, `bestPrice`, `bestMinOrder`, `fitsTargets`, `verifiedSupplier`, `supplierYears`, `why`, `bestOfferUrl`
