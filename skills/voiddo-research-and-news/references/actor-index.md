# Papers, articles, newsletters and podcasts: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Medium Scraper: Articles by User, Tag or Publication

- Actor ID: `v0iddo/medium-rss-tracker`
- Store page: https://apify.com/v0iddo/medium-rss-tracker
- Price: $0.20 per 1,000 results, nothing per run

Pull Medium articles via the public RSS feed endpoints: /feed/@user, /feed/tag/{tag}, /feed/{publication-slug}.

Example input:

```json
{
  "feeds": [
    "@medium",
    "tag/programming",
    "tag/data-science"
  ],
  "maxArticlesPerFeed": 20
}
```

Output fields: `id`, `title`, `link`, `author`, `pubDate`, `summary`, `categories`

## Substack Scraper: Newsletter Posts by Publication

- Actor ID: `v0iddo/substack-newsletter-posts`
- Store page: https://apify.com/v0iddo/substack-newsletter-posts
- Price: $1.06 per 1,000 results, nothing per run

Substack scraper for newsletter posts.

Example input:

```json
{
  "newsletters": [
    "on.substack.com",
    "astralcodexten",
    "www.slowboring.com"
  ]
}
```

Output fields: `newsletter`, `newsletterTitle`, `title`, `link`, `author`, `pubDate`, `summary`

## PubMed Scraper: New Citations by Query

- Actor ID: `v0iddo/pubmed-daily-citations-tracker`
- Store page: https://apify.com/v0iddo/pubmed-daily-citations-tracker
- Price: $1.00 per 1,000 results, nothing per run

Pull daily-new PubMed citations matching any query.

Example input:

```json
{
  "queries": [
    "CRISPR[ti]"
  ],
  "maxResultsPerQuery": 20
}
```

Output fields: `pmid`, `title`, `authors`, `journal`, `year`, `publicationDate`, `entrezDate`, `doi`, `issn`, `volume`, `issue`, `pages`

## Crossref Scraper: Recent Publications by Query

- Actor ID: `v0iddo/crossref-recent-publications`
- Store page: https://apify.com/v0iddo/crossref-recent-publications
- Price: $0.20 per 1,000 results, nothing per run

For each query, pull recent works from Crossref's public REST API with a server-side date filter.

Example input:

```json
{
  "queries": [
    "climate change adaptation",
    "battery recycling"
  ],
  "maxResultsPerQuery": 20
}
```

Output fields: `doi`, `title`, `type`, `subtype`, `publisher`, `container`, `shortContainer`, `issn`, `isbn`, `authors`, `authorCount`, `published`

## News Article Extractor: Full Text from Links and RSS

- Actor ID: `v0iddo/news-scraper`
- Store page: https://apify.com/v0iddo/news-scraper
- Price: $1.50 per 1,000 results, nothing per run

Extract news articles from any publisher.

Example input:

```json
{
  "feedUrls": [
    "https://www.nasa.gov/news-release/feed/"
  ],
  "maxArticlesPerFeed": 10,
  "maxItems": 20
}
```

Output fields: `title`, `publishedAt`, `siteName`, `section`, `language`, `wordCount`, `paywalled`, `url`, `topImage`

## Substack Posts Scraper: Archive, Reactions, Comments

- Actor ID: `v0iddo/substack-scraper`
- Store page: https://apify.com/v0iddo/substack-scraper
- Price: $1.00 per 1,000 results, nothing per run

Collect the posts of any Substack publication: title, subtitle, date, link, paywall flag, reactions, comments, word count and section.

Example input:

```json
{
  "publications": [
    "on.substack.com"
  ],
  "maxItems": 20
}
```

Output fields: `title`, `subtitle`, `date`, `audience`, `reactions`, `comments`, `wordCount`, `section`, `url`
