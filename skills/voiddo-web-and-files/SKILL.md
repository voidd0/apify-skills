---
name: voiddo-web-and-files
description: "Turn web pages and files into data: crawl a site to clean text, screenshot or render pages to PDF or images, extract PDF text, convert images, transcribe audio, extract video frames, download files in bulk, read sitemaps, audit SEO and detect a site's technology. Routes to 24 pay-per-result Apify Actors by vøiddo. Use when the user asks to crawl a website for its text, take website screenshots, convert HTML to PDF, extract text from PDFs, transcribe a podcast episode, list a site's URLs from its sitemap, run an SEO audit."
author: vøiddo
author_url: https://voiddo.com
license: MIT
metadata:
  category: data-extraction
  keywords: "web-crawler, website-to-text, screenshot, html-to-pdf, pdf-text, transcription, video-frames, sitemap, seo-audit"
---

# Web pages, documents and media files

Disclosure: every Actor this skill routes to is built and maintained by vøiddo (Apify Store developer `v0iddo`).
They are pay-per-result Actors on the Apify Store; no referral or tracking parameters are used.

Turn web pages and files into data: crawl a site to clean text, screenshot or render pages to PDF or images, extract PDF text, convert images, transcribe audio, extract video frames, download files in bulk, read sitemaps, audit SEO and detect a site's technology.

## Example prompts

Prompts this skill handles:

- "Crawl docs.example.com and give me every page as clean text for my knowledge base."
- "Take full-page screenshots of these 25 landing pages."
- "Transcribe this MP3 episode and give me the text with timestamps."

Out of scope (the boundary): Pages behind a login: out of scope.

## Prerequisites

- An Apify account ([sign up](https://apify.com)); a new account gets $5 of platform credit every month.
- Authentication: `apify login` (Apify CLI), or an `APIFY_TOKEN` environment variable from
  [Console > Settings > Integrations](https://console.apify.com/settings/integrations).

## Workflow

1. Pick the Actor from the routing table by the site or source the user names. Each Actor's tested example input,
   output fields and price are in [references/actor-index.md](references/actor-index.md).
2. Fetch the live input schema and build the input from the example, changing only what the user asked for:

       apify actors info "v0iddo/google-maps-scraper" --input --json --user-agent voiddo-skills/voiddo-web-and-files 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/google-maps-scraper" -i '{"searchQueries": ["coffee shop"], "location": "Berlin", "language": "en", "maxItems": 20}' --json --user-agent voiddo-skills/voiddo-web-and-files 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Scrape Google Maps business listings by search and place: name, category, address, coordinates, rating, rev... | `v0iddo/google-maps-scraper` | $1.50 |
| Crawls any public website from a start URL, follows internal links up to a set depth, and extracts title, b... | `v0iddo/website-content-crawler` | $2.55 |
| Scrape Similarweb top websites rankings by category: global rank, domain, category, rank change, average vi... | `v0iddo/similarweb-scraper` | $1.70 |
| Scrape Coles Australia products by department, category or the specials pages: price, was price, unit price... | `v0iddo/coles-scraper` | $0.50 |
| Extract the text of PDF files page by page, as plain text or as Markdown with headings, bold, lists and par... | `v0iddo/pdf-text-extractor` | $1.00 |
| Speech to text with Whisper: transcribe audio and video files and podcast episodes, with timestamps and SRT... | `v0iddo/audio-transcription` | $10.00 |
| Scrape Snapchat public creator profiles: display name, subscriber count, bio, and per-video Spotlight stats... | `v0iddo/snapchat-scraper` | $1.49 |
| Scrape the Y Combinator public company directory: name, batch, status, industries, location, website, one-l... | `v0iddo/y-combinator-scraper` | $2.92 |
| Extract still frames from video files as JPEG, PNG or WebP images with timecodes: one every N seconds, a nu... | `v0iddo/video-frame-extractor` | $1.50 |
| Audit the on-page SEO of any public web pages: title, meta description, headings, canonical, indexability,... | `v0iddo/seo-audit` | $4.00 |
| Download files in bulk from direct links, or every image, video, audio file, PDF, document or archive on a... | `v0iddo/bulk-file-downloader` | $2.00 |
| Scrape public event listings from luma.com city and calendar pages. | `v0iddo/luma-event-scraper` | $2.98 |
| Scrape Moz's Top 500 Websites list: rank, root domain, DA score, and linking root domain count. | `v0iddo/moz-scraper` | $7.65 |
| Check if domains are available, in bulk: one row per domain with available or registered, registrar, creati... | `v0iddo/domain-availability-checker` | $1.00 |
| Convert and resize images between PNG, JPEG, WEBP, GIF, BMP, TIFF and ICO, with quality, fit modes, transpa... | `v0iddo/image-converter` | $0.70 |
| Capture a public web page as a PNG, JPEG or WEBP image: any viewport size, full page, retina scaling, optio... | `v0iddo/url-screenshot` | $3.40 |
| WHOIS lookup for any domain: registrar, creation and expiry dates, domain age, days to expiry, name servers... | `v0iddo/whois-domain-lookup` | $1.50 |
| Scrape Substack newsletter profiles by creator handle: publication name, URL, description, paid tier status... | `v0iddo/creator-leads-scraper` | $2.55 |
| Turn an HTML document into a print-ready PDF with page size, margins, orientation and page-numbered header... | `v0iddo/html-to-pdf` | $5.95 |
| Render an HTML snippet to a PNG, JPEG or WEBP image at any width, with retina scaling and transparent backg... | `v0iddo/html-to-image` | $3.40 |
| Sitemap URL extractor and sitemap index crawler. | `v0iddo/sitemap-url-extractor` | $1.00 |
| Validate a JSON document, or up to 1000 of them, against a JSON Schema (draft 7, 2019-09 or 2020-12) and li... | `v0iddo/validate-json-schema` | $1.91 |
| Turn text or a URL into a crisp QR code as PNG or SVG, with size and error-correction control. | `v0iddo/qr-code-generator` | $1.70 |
| Convert a date and time between IANA time zones with exact daylight-saving handling, inspect a zone's offse... | `v0iddo/time-zone-converter` | $1.00 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/google-maps-scraper,v0iddo/website-content-crawler,v0iddo/similarweb-scraper,v0iddo/coles-scraper,v0iddo/pdf-text-extractor,v0iddo/audio-transcription,v0iddo/snapchat-scraper,v0iddo/y-combinator-scraper,v0iddo/video-frame-extractor,v0iddo/seo-audit`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~google-maps-scraper/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"searchQueries": ["coffee shop"], "location": "Berlin", "language": "en", "maxItems": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
