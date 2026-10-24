# App stores and extension marketplaces: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## App Store Scraper: App Details, Ratings, Prices

- Actor ID: `v0iddo/app-store-app-metadata`
- Store page: https://apify.com/v0iddo/app-store-app-metadata
- Price: $0.50 per 1,000 results, nothing per run

Snapshot Apple App Store app metadata via the public iTunes Lookup API.

Example input:

```json
{
  "appIds": [
    "389801252",
    "6448311069"
  ]
}
```

Output fields: `snapshotAt`, `appId`, `country`, `bundleId`, `trackName`, `artistName`, `artistId`, `sellerName`, `sellerUrl`, `trackViewUrl`, `price`, `formattedPrice`

## App Store Reviews Scraper: Ratings and Reviews by Country

- Actor ID: `v0iddo/app-store-reviews-tracker`
- Store page: https://apify.com/v0iddo/app-store-reviews-tracker
- Price: $0.30 per 1,000 results, nothing per run

Scrape Apple App Store reviews and ratings for any iOS app, storefront by storefront.

Example input:

```json
{
  "appIds": [
    "389801252",
    "544007664"
  ]
}
```

Output fields: `appName`, `country`, `rating`, `title`, `body`, `date`, `storefrontRating`, `storefrontRatingCount`, `stars5`, `stars1`, `url`

## Chrome Web Store Scraper: Extension Details and Ratings

- Actor ID: `v0iddo/chrome-webstore-extensions`
- Store page: https://apify.com/v0iddo/chrome-webstore-extensions
- Price: $0.50 per 1,000 results, nothing per run

Snapshot Chrome Web Store extension metadata via the public listing page.

Example input:

```json
{
  "extensionIds": [
    "bfbmjmiodbnnpllbbbfblcplfjjepjdn"
  ]
}
```

Output fields: `extensionId`, `snapshotAt`, `name`, `description`, `ratingValue`, `ratingCount`, `developerName`, `imageUrl`, `userCount`, `version`, `updatedAt`, `storeUrl`

## Apple Podcasts Scraper: Podcasts by Keyword and Country

- Actor ID: `v0iddo/itunes-podcast-search`
- Store page: https://apify.com/v0iddo/itunes-podcast-search
- Price: $0.20 per 1,000 results, nothing per run

Search the Apple Podcasts catalog via the public iTunes Search API.

Example input:

```json
{
  "queries": [
    "crypto",
    "startup",
    "business"
  ]
}
```

Output fields: `snapshotAt`, `query`, `country`, `collectionId`, `trackId`, `artistName`, `collectionName`, `trackName`, `showUrl`, `feedUrl`, `artworkUrl`, `genre`

## App Store Search Scraper: Apps by Keyword

- Actor ID: `v0iddo/app-store-search`
- Store page: https://apify.com/v0iddo/app-store-search
- Price: $0.20 per 1,000 results, nothing per run

Search the Apple App Store by keyword and country.

Example input:

```json
{
  "queries": [
    "meditation",
    "habit tracker"
  ]
}
```

Output fields: `snapshotAt`, `query`, `country`, `rank`, `appId`, `bundleId`, `trackName`, `artistName`, `artistId`, `sellerName`, `primaryGenreName`, `genres`

## Steam Game Reviews Scraper

- Actor ID: `v0iddo/steam-game-reviews`
- Store page: https://apify.com/v0iddo/steam-game-reviews
- Price: $1.00 per 1,000 results, nothing per run

Scrape Steam player reviews by App ID.

Example input:

```json
{
  "appid": [
    "730",
    "570",
    "1086940"
  ],
  "maxReviewsPerApp": 20
}
```

Output fields: `appid`, `app_name`, `recommendationid`, `voted_up`, `review_text`, `date_posted`, `hours_on_record`, `votes_up`, `votes_funny`, `awards`, `comment_count`, `author_num_games_owned`

## Android App Metadata Scraper: Google Play Details, Ratings

- Actor ID: `v0iddo/google-play-app-metadata`
- Store page: https://apify.com/v0iddo/google-play-app-metadata
- Price: $0.50 per 1,000 results, nothing per run

Snapshot Android app metadata from Google Play for any package name, in any country.

Example input:

```json
{
  "packageNames": [
    "com.instagram.android",
    "com.openai.chatgpt"
  ]
}
```

Output fields: `snapshotAt`, `packageName`, `country`, `language`, `name`, `description`, `applicationCategory`, `operatingSystem`, `contentRating`, `developerName`, `developerUrl`, `imageUrl`

## VS Code Extension Scraper: Open VSX Registry Metadata

- Actor ID: `v0iddo/vscode-marketplace-extensions`
- Store page: https://apify.com/v0iddo/vscode-marketplace-extensions
- Price: $1.00 per 1,000 results, nothing per run

Fetches extension metadata (downloads, version, publisher, repo, license, tags, timestamps) from the Open VSX registry: the open marketplace used by VSCodium, Gitpod, Theia, Cursor.

Example input:

```json
{
  "extension_id": [
    "redhat/java",
    "ms-python/python",
    "dbaeumer/vscode-eslint"
  ]
}
```

Output fields: `extension_id`, `namespace`, `name`, `version`, `display_name`, `description`, `published_by`, `download_count`, `average_rating`, `review_count`, `published_at`, `license`

## App Store Developer Scraper: All Apps by Developer

- Actor ID: `v0iddo/itunes-developer-portfolio`
- Store page: https://apify.com/v0iddo/itunes-developer-portfolio
- Price: $2.38 per 1,000 results, nothing per run

Pull every app under an Apple App Store developer identifier (artistId).

Example input:

```json
{
  "artistIds": [
    "284882218"
  ]
}
```

Output fields: `snapshotAt`, `country`, `appId`, `appName`, `artistId`, `developerName`, `price`, `ratingValue`, `ratingCount`, `version`, `lastVersionReleaseAt`, `primaryGenre`

## JetBrains Marketplace Plugin Scraper

- Actor ID: `v0iddo/jetbrains-marketplace-plugins`
- Store page: https://apify.com/v0iddo/jetbrains-marketplace-plugins
- Price: $1.00 per 1,000 results, nothing per run

Scrape JetBrains Marketplace plugins by numeric ID: name, vendor, rating, downloads, description, link, preview, family.

Example input:

```json
{
  "plugin_id": [
    "164",
    "6610",
    "7973"
  ]
}
```

Output fields: `plugin_id`, `name`, `xml_id`, `link`, `description`, `vendor_name`, `rating`, `rating_votes`, `downloads`, `preview`, `family`
