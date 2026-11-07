# Web pages, documents and media files: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Google Maps Scraper: Places, Phones, Hours

- Actor ID: `v0iddo/google-maps-scraper`
- Store page: https://apify.com/v0iddo/google-maps-scraper
- Price: $1.50 per 1,000 results, nothing per run

Scrape Google Maps business listings by search and place: name, category, address, coordinates, rating, review count, phone, website, opening hours, place ID and Maps link.

Example input:

```json
{
  "searchQueries": [
    "coffee shop"
  ],
  "location": "Berlin",
  "language": "en",
  "maxItems": 20
}
```

Output fields: `name`, `category`, `address`, `city`, `rating`, `reviewsCount`, `phone`, `website`, `latitude`, `longitude`, `placeId`, `url`

## Website Content Crawler: Pages to Clean Text

- Actor ID: `v0iddo/website-content-crawler`
- Store page: https://apify.com/v0iddo/website-content-crawler
- Price: $2.55 per 1,000 results, nothing per run

Crawls any public website from a start URL, follows internal links up to a set depth, and extracts title, breadcrumbs, clean text body, and word count.

Example input:

```json
{
  "startUrls": [
    "https://docs.python.org/3/library/"
  ],
  "maxDepth": 1,
  "maxPagesPerUrl": 15,
  "maxItems": 20
}
```

Output fields: `url`, `title`, `h1`, `breadcrumbs`, `description`, `textContent`, `wordCount`, `depth`

## Similarweb Scraper: Top Websites by Category

- Actor ID: `v0iddo/similarweb-scraper`
- Store page: https://apify.com/v0iddo/similarweb-scraper
- Price: $1.70 per 1,000 results, nothing per run

Scrape Similarweb top websites rankings by category: global rank, domain, category, rank change, average visit duration, pages per visit, and bounce rate.

Example input:

```json
{
  "categorySlugs": [
    "",
    "computers-electronics-and-technology",
    "arts-and-entertainment"
  ],
  "maxItems": 20
}
```

Output fields: `rank`, `domain`, `category`, `categorySlug`, `rankingList`, `rankChange`, `avgVisitDuration`, `avgVisitDurationSeconds`, `pagesPerVisit`, `bounceRate`, `url`

## Coles Price Scraper: Specials, Unit Prices

- Actor ID: `v0iddo/coles-scraper`
- Store page: https://apify.com/v0iddo/coles-scraper
- Price: $0.50 per 1,000 results, nothing per run

Scrape Coles Australia products by department, category or the specials pages: price, was price, unit price, half price and multibuy offers, stock, purchase limits and aisle.

Example input:

```json
{
  "categories": [
    "dairy-eggs-fridge/yoghurt"
  ],
  "maxItems": 20
}
```

Output fields: `productId`, `name`, `brand`, `size`, `price`, `wasPrice`, `unitPrice`, `unitMeasure`, `available`, `url`

## Internshala Scraper

- Actor ID: `v0iddo/internshala-scraper`
- Store page: https://apify.com/v0iddo/internshala-scraper
- Price: $0.34 per 1,000 results, nothing per run

Scrape internshala.com for internships and fresher jobs: title, company, location, stipend, duration, work-from-home flag, and direct URL.

Example input:

```json
{
  "startUrls": [
    "https://internshala.com/internships/computer-science-internship/"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `title`, `company`, `location`, `workFromHome`, `stipend`, `duration`, `listingType`, `postedOn`, `url`

## Audio Transcription: Audio to Text Converter, Podcast, Video

- Actor ID: `v0iddo/audio-transcription`
- Store page: https://apify.com/v0iddo/audio-transcription
- Price: $10.00 per 1,000 results, nothing per run

Speech to text with Whisper: transcribe audio and video files and podcast episodes, with timestamps and SRT or VTT subtitles.

Example input:

```json
{
  "mediaUrls": [
    "https://upload.wikimedia.org/wikipedia/commons/5/50/Jfk_rice_university_we_choose_to_go_to_the_moon.ogg"
  ],
  "maxMinutesPerFile": 8,
  "maxItems": 1
}
```

Output fields: `fileName`, `episodeTitle`, `language`, `durationSeconds`, `billedMinutes`, `wordCount`, `text`, `mediaUrl`

## Extract Text from PDF: Markdown & Metadata

- Actor ID: `v0iddo/pdf-text-extractor`
- Store page: https://apify.com/v0iddo/pdf-text-extractor
- Price: $1.00 per 1,000 results, nothing per run

Extract the text of PDF files page by page, as plain text or as Markdown with headings, bold, lists and paragraphs, ready for LLM and search pipelines.

Example input:

```json
{
  "file_urls": [
    "https://www.irs.gov/pub/irs-pdf/fw9.pdf"
  ],
  "format": "markdown"
}
```

Output fields: `index`, `page_count`, `chars`, `pages`, `metadata`

## Snapchat Profile and Spotlight Scraper

- Actor ID: `v0iddo/snapchat-scraper`
- Store page: https://apify.com/v0iddo/snapchat-scraper
- Price: $1.49 per 1,000 results, nothing per run

Scrape Snapchat public creator profiles: display name, subscriber count, bio, and per-video Spotlight stats including view count, like count, comment count, share count, upload date, duration, and thumbnail.

Example input:

```json
{
  "handles": [
    "kyliejenner",
    "daviddobrik"
  ],
  "maxItems": 20
}
```

Output fields: `handle`, `displayName`, `subscriberCount`, `videoTitle`, `viewCount`, `likeCount`, `uploadDate`, `durationSecs`, `thumbnailUrl`, `url`

## Extract Frames from Video: Video Frame Extractor, Thumbnails

- Actor ID: `v0iddo/video-frame-extractor`
- Store page: https://apify.com/v0iddo/video-frame-extractor
- Price: $1.50 per 1,000 results, nothing per run

Extract still frames from video files as JPEG, PNG or WebP images with timecodes: one every N seconds, a number evenly spaced, exact times, one per scene or every keyframe, plus a contact sheet.

Example input:

```json
{
  "videoUrls": [
    "https://upload.wikimedia.org/wikipedia/commons/8/86/Modern_Times_trailer_%281936%29.webm"
  ],
  "mode": "count",
  "frameCount": 20,
  "maxItems": 20
}
```

Output fields: `imageUrl`, `timecode`, `frameNumber`, `kind`, `videoFile`, `imageWidth`, `imageHeight`, `videoDurationSeconds`

## Y Combinator Company Directory Scraper

- Actor ID: `v0iddo/y-combinator-scraper`
- Store page: https://apify.com/v0iddo/y-combinator-scraper
- Price: $1.27 per 1,000 results, nothing per run

Scrape the Y Combinator public company directory: name, batch, status, industries, location, website, one-liner, team size, open job count, and YC profile link.

Example input:

```json
{
  "companyUrls": [
    "https://www.ycombinator.com/companies/stripe",
    "https://www.ycombinator.com/companies/airbnb",
    "https://www.ycombinator.com/companies/dropbox",
    "https://www.ycombinator.com/companies/reddit",
    "https://www.ycombinator.com/companies/doordash",
    "https://www.ycombinator.com/companies/coinbase",
    "https://www.ycombinator.com/companies/instacart",
    "https://www.ycombinator.com/companies/gitlab",
    "https://www.ycombinator.com/companies/gusto",
    "https://www.ycombinator.com/companies/brex",
    "https://www.ycombinator.com/companies/openai",
    "https://www.ycombinator.com/companies/figma"
  ],
  "maxItems": 20
}
```

Output fields: `name`, `batch`, `status`, `industries`, `location`, `website`, `oneLiner`, `teamSize`, `jobCount`, `url`

## Bluesky Scraper

- Actor ID: `v0iddo/bluesky-scraper`
- Store page: https://apify.com/v0iddo/bluesky-scraper
- Price: $0.85 per 1,000 results, nothing per run

Scrape public Bluesky accounts: posts with text, like count, repost count, reply count, language, media flag, and timestamp.

Example input:

```json
{
  "handles": [
    "bsky.app"
  ],
  "postsPerHandle": 20,
  "maxItems": 20
}
```

Output fields: `postUri`, `url`, `handle`, `did`, `text`, `likeCount`, `repostCount`, `replyCount`, `indexedAt`, `hasMedia`, `lang`

## SEO Audit Tool (On-Page Checker, Canonical, Alt Text)

- Actor ID: `v0iddo/seo-audit`
- Store page: https://apify.com/v0iddo/seo-audit
- Price: $4.00 per 1,000 results, nothing per run

Audit the on-page SEO of any public web pages: title, meta description, headings, canonical, indexability, structured data types, image alt text, link counts and social tags, with a list of issues and a 0 to 100 score per page.

Example input:

```json
{
  "startUrls": [
    "https://www.python.org/",
    "https://docs.python.org/3/",
    "https://www.joelonsoftware.com/"
  ],
  "maxPagesPerSite": 5,
  "maxItems": 20
}
```

Output fields: `url`, `statusCode`, `score`, `indexable`, `title`, `titleLength`, `metaDescriptionLength`, `h1Count`, `wordCount`, `imagesMissingAlt`, `internalLinks`, `externalLinks`, `canonicalIsSelf`, `issues`

## Hiring.Cafe Jobs Scraper

- Actor ID: `v0iddo/hiring-cafe-scraper`
- Store page: https://apify.com/v0iddo/hiring-cafe-scraper
- Price: $1.00 per 1,000 results, nothing per run

Scrape job listings from Hiring.Cafe: title, company, location, workplace type, seniority, job category, technical tools, requirements summary, visa sponsorship, and apply link.

Example input:

```json
{
  "keyword": "software engineer",
  "maxItems": 20
}
```

Output fields: `jobTitle`, `companyName`, `location`, `workplaceType`, `seniorityLevel`, `employmentType`, `jobCategory`, `technicalTools`, `applyUrl`, `url`

## Bulk File Downloader and Image Downloader: Web Pages, PDFs

- Actor ID: `v0iddo/bulk-file-downloader`
- Store page: https://apify.com/v0iddo/bulk-file-downloader
- Price: $2.00 per 1,000 results, nothing per run

Download files in bulk from direct links, or every image, video, audio file, PDF, document or archive on a list of web pages.

Example input:

```json
{
  "pageUrls": [
    "https://en.wikipedia.org/wiki/Hummingbird"
  ],
  "fileTypes": [
    "image"
  ],
  "maxFilesPerPage": 20,
  "maxItems": 20
}
```

Output fields: `fileUrl`, `fileName`, `fileType`, `fileBytes`, `imageWidth`, `imageHeight`, `altText`, `url`, `error`

## Luma Event Scraper

- Actor ID: `v0iddo/luma-event-scraper`
- Store page: https://apify.com/v0iddo/luma-event-scraper
- Price: $2.38 per 1,000 results, nothing per run

Scrape public event listings from luma.com city and calendar pages.

Example input:

```json
{
  "pageUrls": [
    "https://luma.com/nyc",
    "https://luma.com/sf"
  ],
  "maxItems": 20
}
```

Output fields: `name`, `startDate`, `endDate`, `locationType`, `city`, `fullAddress`, `latitude`, `longitude`, `price`, `priceCurrency`, `soldOut`, `url`

## Moz Top 500 Scraper: Domain Rankings

- Actor ID: `v0iddo/moz-scraper`
- Store page: https://apify.com/v0iddo/moz-scraper
- Price: $0.85 per 1,000 results, nothing per run

Scrape Moz's Top 500 Websites list: rank, root domain, DA score, and linking root domain count.

Example input:

```json
{
  "minDaScore": 0,
  "maxRank": 500,
  "maxItems": 20
}
```

Output fields: `rank`, `rootDomain`, `daScore`, `linkingRootDomains`, `externalUrl`, `url`

## North Data Scraper

- Actor ID: `v0iddo/north-data-scraper`
- Store page: https://apify.com/v0iddo/north-data-scraper
- Price: $2.98 per 1,000 results, nothing per run

Extract European company profiles from northdata.com: company name, register number, court, LEI code, address, founding date, corporate purpose, and officer count.

Example input:

```json
{
  "companyUrls": [
    "https://www.northdata.com/BMW-AG,+M%C3%BCnchen/HRB+42243",
    "https://www.northdata.com/Volkswagen+AG,+Wolfsburg/HRB+100484",
    "https://www.northdata.com/Siemens+AG,+M%C3%BCnchen/HRB+6684",
    "https://www.northdata.com/Deutsche+Telekom+AG,+Bonn/HRB+6794",
    "https://www.northdata.com/BASF+SE,+Ludwigshafen+am+Rhein/HRB+6729",
    "https://www.northdata.com/Bayer+AG,+Leverkusen/HRB+48248",
    "https://www.northdata.com/Allianz+SE,+M%C3%BCnchen/HRB+164232",
    "https://www.northdata.com/SAP+SE,+Walldorf/HRB+755676",
    "https://www.northdata.com/Mercedes-Benz+Group+AG,+Stuttgart/HRB+19360",
    "https://www.northdata.com/Deutsche+Bank+AG,+Frankfurt+am+Main/HRB+30000"
  ],
  "maxItems": 20
}
```

Output fields: `name`, `registerNumber`, `registerCourt`, `leiCode`, `street`, `city`, `postalCode`, `country`, `foundingDate`, `corporatePurpose`, `officerCount`, `url`

## Domain Availability Checker: Bulk RDAP

- Actor ID: `v0iddo/domain-availability-checker`
- Store page: https://apify.com/v0iddo/domain-availability-checker
- Price: $1.00 per 1,000 results, nothing per run

Check if domains are available, in bulk: one row per domain with available or registered, registrar, creation and expiry dates and days to expiry, straight from the registry that runs the TLD (RDAP).

Example input:

```json
{
  "domains": [
    "google.com",
    "github.com",
    "wikipedia.org",
    "python.org",
    "mozilla.org",
    "voiddo.com",
    "bbc.com",
    "example.net",
    "voiddo-availability-sample-7q3.com",
    "voiddo-availability-sample-7q3.org",
    "shop.github.com"
  ],
  "maxItems": 20
}
```

Output fields: `domain`, `available`, `status`, `registrar`, `expirationDate`, `daysToExpiry`, `registrationDate`, `note`

## Image Converter: WEBP to PNG, PNG to JPG, JPG to WEBP, GIF

- Actor ID: `v0iddo/image-converter`
- Store page: https://apify.com/v0iddo/image-converter
- Price: $0.70 per 1,000 results, nothing per run

Convert and resize images between PNG, JPEG, WEBP, GIF, BMP, TIFF and ICO, with quality, fit modes, transparency handling and optional metadata stripping.

Example input:

```json
{
  "file_base64": "iVBORw0KGgoAAAANSUhEUgAAABgAAAAQCAYAAAAMJL+VAAAATUlEQVR42mOUX1z1n/UvEwOtMBMDjcHQt4AFl8TOpDSSDGqu2jTIfAADgTPm4U0lPbUhwzySBz4O1mckDVEfuM+bRVq5g8Oto6mIIAAA89w1GtnVjpwAAAAASUVORK5CYII=",
  "to": "webp",
  "width": 48,
  "quality": 90
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## Made-in-China.com Product Scraper

- Actor ID: `v0iddo/made-in-china-scraper`
- Store page: https://apify.com/v0iddo/made-in-china-scraper
- Price: $0.85 per 1,000 results, nothing per run

Scrape Made-in-China.com product search pages by keyword.

Example input:

```json
{
  "keywords": [
    "LED Light",
    "Solar Panel"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `keyword`, `page`, `position`, `name`, `category`, `lowPriceUsd`, `highPriceUsd`, `supplierName`, `inStock`, `image`, `url`

## Myntra Product Scraper

- Actor ID: `v0iddo/myntra-product-scraper`
- Store page: https://apify.com/v0iddo/myntra-product-scraper
- Price: $1.00 per 1,000 results, nothing per run

Scrape Myntra category and search listing pages into product rows: product ID, name, brand, price, MRP, discount percent, rating, sizes, category, image, and product URL.

Example input:

```json
{
  "categoryUrls": [
    "https://www.myntra.com/men-tshirts"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `productId`, `name`, `brand`, `price`, `mrp`, `discountPercent`, `rating`, `ratingCount`, `sizes`, `category`, `image`, `url`

## CarGurus Zipcode Search Scraper

- Actor ID: `v0iddo/cargurus-zipcode-search-scraper`
- Store page: https://apify.com/v0iddo/cargurus-zipcode-search-scraper
- Price: $0.85 per 1,000 results, nothing per run

Scrape CarGurus vehicle search pages by ZIP code: VIN, make, model, year, trim, price, MSRP, mileage, fuel economy, dealer name and location, and direct listing link.

Example input:

```json
{
  "searchUrls": [
    "https://www.cargurus.com/Cars/new/nl-New-Ford-Mustang-d2"
  ],
  "zipCode": "10001",
  "radiusMiles": 100,
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `listingId`, `vin`, `year`, `make`, `model`, `trim`, `price`, `msrp`, `mileage`, `dealerName`, `dealerState`, `url`

## HTML to Image Converter: Convert HTML to PNG, JPG and WEBP

- Actor ID: `v0iddo/html-to-image`
- Store page: https://apify.com/v0iddo/html-to-image
- Price: $3.40 per 1,000 results, nothing per run

Render an HTML snippet to a PNG, JPEG or WEBP image at any width, with retina scaling and transparent background.

Example input:

```json
{
  "html": "<div style='font:700 48px sans-serif;padding:40px;background:#1fa37a;color:#fff'>Hello, v&oslash;iddo</div>",
  "width": 600,
  "height": 200
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## TheFork Restaurant Reviews Scraper

- Actor ID: `v0iddo/thefork-restaurant-reviews-scraper`
- Store page: https://apify.com/v0iddo/thefork-restaurant-reviews-scraper
- Price: $1.70 per 1,000 results, nothing per run

Scrape TheFork city listing pages into restaurant rows: name, cuisine, address, TheFork rating, review count, average price, price range level, Michelin distinctions, booking status, and a direct link.

Example input:

```json
{
  "cityUrls": [
    "https://www.thefork.com/restaurants/paris-c415144"
  ],
  "maxItems": 20
}
```

Output fields: `restaurantId`, `name`, `cuisine`, `address`, `rating`, `reviewCount`, `avgPriceEur`, `priceRangeLevel`, `distinctions`, `imageUrl`, `url`

## Substack Newsletter Scraper

- Actor ID: `v0iddo/creator-leads-scraper`
- Store page: https://apify.com/v0iddo/creator-leads-scraper
- Price: $1.53 per 1,000 results, nothing per run

Scrape Substack newsletter profiles by creator handle: publication name, URL, description, paid tier status, community flag, homepage type, logo, and creation date.

Example input:

```json
{
  "handles": [
    "stratechery",
    "noahpinion",
    "astralcodexten",
    "mattstoller",
    "platformer",
    "byrnehobart",
    "worksinprogress",
    "slowboring",
    "persuasion",
    "thedispatch"
  ],
  "maxItems": 20
}
```

Output fields: `publicationName`, `publicationUrl`, `subdomain`, `description`, `hasPaidTier`, `paymentsState`, `homepageType`, `communityEnabled`, `createdAt`, `logoUrl`

## Website Screenshot Generator: URL to PNG, JPEG or WEBP

- Actor ID: `v0iddo/url-screenshot`
- Store page: https://apify.com/v0iddo/url-screenshot
- Price: $3.40 per 1,000 results, nothing per run

Capture a public web page as a PNG, JPEG or WEBP image: any viewport size, full page, retina scaling, optional cookie-banner hiding.

Example input:

```json
{
  "url": "https://example.com"
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## DuckDuckGo Search Scraper

- Actor ID: `v0iddo/duckduckgo-scraper`
- Store page: https://apify.com/v0iddo/duckduckgo-scraper
- Price: $0.51 per 1,000 results, nothing per run

Scrape DuckDuckGo web search results into structured rows: title, URL, snippet, position, and query.

Example input:

```json
{
  "queries": [
    "web scraping tools",
    "python tutorial"
  ],
  "region": "us-en",
  "maxPages": 1,
  "safeSearch": "moderate",
  "maxItems": 20
}
```

Output fields: `query`, `position`, `title`, `url`, `displayUrl`, `snippet`, `page`

## Convert HTML to PDF (A4, Letter, Legal, A3 and more)

- Actor ID: `v0iddo/html-to-pdf`
- Store page: https://apify.com/v0iddo/html-to-pdf
- Price: $3.40 per 1,000 results, nothing per run

Turn an HTML document into a print-ready PDF with page size, margins, orientation and page-numbered header and footer.

Example input:

```json
{
  "html": "<h1>Invoice #1042</h1><p>Total due: 120.00 USD, payable within 14 days.</p>"
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## WHOIS Domain Lookup: Registrar, Age, Expiry, Name Servers

- Actor ID: `v0iddo/whois-domain-lookup`
- Store page: https://apify.com/v0iddo/whois-domain-lookup
- Price: $1.50 per 1,000 results, nothing per run

WHOIS lookup for any domain: registrar, creation and expiry dates, domain age, days to expiry, name servers, status and DNSSEC, read live from the registry's RDAP service.

Example input:

```json
{
  "query": "github.com"
}
```

Output fields: `index`, `query`, `ldhName`, `registrar`, `events`, `age_days`, `days_to_expiry`, `status`, `nameservers`, `dnssec`

## PeoplePerHour Job Scraper

- Actor ID: `v0iddo/peopleperhour-job-scraper`
- Store page: https://apify.com/v0iddo/peopleperhour-job-scraper
- Price: $0.85 per 1,000 results, nothing per run

Scrape freelance job listings from PeoplePerHour category pages: title, description, budget, currency, project type, category, proposal count, posted date, expiry date and job URL.

Example input:

```json
{
  "categorySlugs": [
    "technology"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `jobId`, `title`, `budget`, `currency`, `projectType`, `category`, `subCategory`, `proposalCount`, `postedAt`, `expiresAt`, `description`, `url`

## JobTeaser Job Scraper

- Actor ID: `v0iddo/jobteaser-job-scraper`
- Store page: https://apify.com/v0iddo/jobteaser-job-scraper
- Price: $0.79 per 1,000 results, nothing per run

Scrape job listings from jobteaser.com: title, company, location, contract type, posted time, easy-apply and featured flags, company logo, and direct apply link.

Example input:

```json
{
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `jobId`, `title`, `company`, `location`, `contractType`, `postedAt`, `easyApply`, `featured`, `companyLogoUrl`, `url`

## Rakuten Ichiba Listings Scraper

- Actor ID: `v0iddo/rakuten-japan-listings-scraper`
- Store page: https://apify.com/v0iddo/rakuten-japan-listings-scraper
- Price: $1.28 per 1,000 results, nothing per run

Scrape Rakuten Ichiba search results into product rows: title, JPY price, shop name, review score, review count, Rakuten points, shipping included flag, sold-out flag, item URL, and thumbnail image.

Example input:

```json
{
  "keywords": [
    "カメラ"
  ],
  "maxPages": 1,
  "maxItems": 20
}
```

Output fields: `title`, `price`, `shopName`, `reviewScore`, `reviewCount`, `points`, `freeShipping`, `isSoldOut`, `image`, `url`

## Eluta.ca Job Scraper

- Actor ID: `v0iddo/eluta-ca-job-scraper`
- Store page: https://apify.com/v0iddo/eluta-ca-job-scraper
- Price: $0.77 per 1,000 results, nothing per run

Scrape Canadian job listings from eluta.ca by keyword and location.

Example input:

```json
{
  "keyword": "software developer",
  "location": "Toronto ON",
  "maxPages": 2,
  "maxItems": 20
}
```

Output fields: `jobId`, `title`, `employer`, `location`, `remote`, `salaryMin`, `salaryMax`, `topEmployer`, `snippet`, `lastSeen`, `url`

## Sitemap URL Extractor: Robots.txt and Sitemap Index to URLs

- Actor ID: `v0iddo/sitemap-url-extractor`
- Store page: https://apify.com/v0iddo/sitemap-url-extractor
- Price: $1.00 per 1,000 results, nothing per run

Sitemap URL extractor and sitemap index crawler.

Example input:

```json
{
  "domains": [
    "stripe.com",
    "shopify.com",
    "vercel.com"
  ],
  "maxUrlsPerDomain": 20
}
```

Output fields: `domain`, `url`, `lastmod`, `changefreq`, `priority`, `source`

## JSON Schema Validator: Bulk, Draft 7, 2019-09, 2020-12

- Actor ID: `v0iddo/validate-json-schema`
- Store page: https://apify.com/v0iddo/validate-json-schema
- Price: $1.27 per 1,000 results, nothing per run

Validate a JSON document, or up to 1000 of them, against a JSON Schema (draft 7, 2019-09 or 2020-12) and list every error with its path.

Example input:

```json
{
  "schema": {
    "type": "object",
    "required": [
      "name",
      "age"
    ],
    "properties": {
      "name": {
        "type": "string"
      },
      "age": {
        "type": "integer",
        "minimum": 0
      }
    }
  },
  "instance": "{\"name\": \"Ada\", \"age\": -3}"
}
```

Output fields: `index`, `valid`, `count`, `errors`

## QR Code Generator (PNG and SVG)

- Actor ID: `v0iddo/qr-code-generator`
- Store page: https://apify.com/v0iddo/qr-code-generator
- Price: $1.70 per 1,000 results, nothing per run

Turn text or a URL into a crisp QR code as PNG or SVG, with size and error-correction control.

Example input:

```json
{
  "text": "https://utils.voiddo.com",
  "format": "png",
  "size": 256
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## Time Zone Converter: IANA Zones, DST, Offsets, Batch

- Actor ID: `v0iddo/time-zone-converter`
- Store page: https://apify.com/v0iddo/time-zone-converter
- Price: $1.00 per 1,000 results, nothing per run

Convert a date and time between IANA time zones with exact daylight-saving handling, inspect a zone's offset and transitions, or list a country's zones.

Example input:

```json
{
  "op": "convert",
  "datetime": "2026-03-29T01:30:00",
  "from_tz": "Europe/Berlin",
  "to_tz": "America/New_York"
}
```

Output fields: `index`, `input`, `from_tz`, `output`, `offset_from`, `offset_to`, `dst_to`, `day_offset`
