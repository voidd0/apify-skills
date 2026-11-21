---
name: voiddo-web-and-files
description: "Turn web pages and files into data: crawl a site to clean text, screenshot or render pages to PDF or images, extract PDF text, convert images, transcribe audio, extract video frames, download files in bulk, read sitemaps, audit SEO and detect a site's technology. Routes to 51 pay-per-result Apify Actors by vøiddo. Use when the user asks to crawl a website for its text, take website screenshots, convert HTML to PDF, extract text from PDFs, transcribe a podcast episode, list a site's URLs from its sitemap, run an SEO audit."
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
| Crawls any public website from a start URL, follows internal links up to a set depth, and extracts title, b... | `v0iddo/website-content-crawler` | $2.29 |
| Scrape Similarweb top websites rankings by category: global rank, domain, category, rank change, average vi... | `v0iddo/similarweb-scraper` | $1.70 |
| Scrape Coles Australia products by department, category or the specials pages: price, was price, unit price... | `v0iddo/coles-scraper` | $0.50 |
| Speech to text with Whisper: transcribe audio and video files and podcast episodes, with timestamps and SRT... | `v0iddo/audio-transcription` | $10.00 |
| Scrape internshala.com for internships and fresher jobs: title, company, location, stipend, duration, work-... | `v0iddo/internshala-scraper` | $1.36 |
| Extract the text of PDF files page by page, as plain text or as Markdown with headings, bold, lists and par... | `v0iddo/pdf-text-extractor` | $2.55 |
| Scrape Snapchat public creator profiles: name, subscribers, bio, and per-video Spotlight stats: views, like... | `v0iddo/snapchat-scraper` | $1.69 + $0.001/start |
| Extract still frames from video files as JPEG, PNG or WebP images with timecodes: one every N seconds, a nu... | `v0iddo/video-frame-extractor` | $1.50 |
| Scrape the Y Combinator public company directory: name, batch, status, industries, location, website, one-l... | `v0iddo/y-combinator-scraper` | $0.13 |
| Scrape Moz's Top 500 Websites list: rank, root domain, DA score, and linking root domain count. | `v0iddo/moz-scraper` | $0.85 |
| Download files in bulk from links, web pages, a CSV or Google Sheet, or another actor's dataset: images, vi... | `v0iddo/bulk-file-downloader` | $2.00 |
| Scrape job listings from Hiring.Cafe: title, company, location, workplace type, seniority, job category, te... | `v0iddo/hiring-cafe-scraper` | $1.00 |
| Scrape public Bluesky accounts: posts with text, like count, repost count, reply count, language, media fla... | `v0iddo/bluesky-scraper` | $1.27 |
| Scrape public event listings from luma.com city and calendar pages. | `v0iddo/luma-event-scraper` | $2.38 |
| Audit the on-page SEO of any public web pages: title, meta description, headings, canonical, indexability,... | `v0iddo/seo-audit` | $6.80 |
| Scrape job listings from Apna.co in India: title, company, city and area, monthly salary range in INR, offi... | `v0iddo/apna-co-scraper` | $0.78 |
| Scrape France Travail (ex Pole Emploi) job offers by town or department, ROME domain and contract type: tit... | `v0iddo/francetravail` | $1.00 |
| Check if domains are available, in bulk: one row per domain with available or registered, registrar, creati... | `v0iddo/domain-availability-checker` | $1.00 |
| Extract European company profiles from northdata.com: company name, register number, court, LEI code, addre... | `v0iddo/north-data-scraper` | $3.82 |
| Convert and resize images between PNG, JPEG, WEBP, GIF, BMP, TIFF and ICO, with quality, fit modes, transpa... | `v0iddo/image-converter` | $1.71 |
| Scrape Made-in-China.com product search pages by keyword. | `v0iddo/made-in-china-scraper` | $1.44 |
| Scrape Substack newsletter profiles by creator handle: publication name, URL, description, paid tier status... | `v0iddo/creator-leads-scraper` | $2.29 |
| Scrape the ForexFactory economic calendar into rows with date, time (ET), currency, impact level, event nam... | `v0iddo/forexfactory-economic-calendar` | $1.70 |
| Scrape Myntra category and search listing pages into product rows: product ID, name, brand, price, MRP, dis... | `v0iddo/myntra-product-scraper` | $2.29 |
| Scrape DuckDuckGo web search results into structured rows: title, URL, snippet, position, and query. | `v0iddo/duckduckgo-scraper` | $0.51 |
| Capture a public web page as a PNG, JPEG or WEBP image: any viewport size, full page, retina scaling, optio... | `v0iddo/url-screenshot` | $3.40 |
| WHOIS lookup for any domain: registrar, creation and expiry dates, domain age, days to expiry, name servers... | `v0iddo/whois-domain-lookup` | $1.70 |
| Turn an HTML document into a print-ready PDF with page size, margins, orientation and page-numbered header... | `v0iddo/html-to-pdf` | $3.40 |
| Scrape CarGurus vehicle search pages by ZIP code: VIN, make, model, year, trim, price, MSRP, mileage, fuel... | `v0iddo/cargurus-zipcode-search-scraper` | $0.85 |
| Scrape Indian listed company fundamentals from screener.in: market cap, P/E, ROCE, ROE, book value, dividen... | `v0iddo/screener-in-scraper` | $8.50 |
| Scrape job listings from jobteaser.com: title, company, location, contract type, posted time, easy-apply an... | `v0iddo/jobteaser-job-scraper` | $0.79 |
| Scrape freelance job listings from PeoplePerHour category pages: title, description, budget, currency, proj... | `v0iddo/peopleperhour-job-scraper` | $0.85 |
| Scrape tennis scores: ATP and WTA match results of any day with set by set scores, tiebreaks, winner and pr... | `v0iddo/tennis-scores-api` | $4.59 |
| Scrape PriceCharting prices for video games, Pokemon and other trading cards, comics, coins, Funko Pops and... | `v0iddo/pricecharting-product-scraper` | $2.13 |
| Scrape Canadian job listings from eluta.ca by keyword and location. | `v0iddo/eluta-ca-job-scraper` | $0.77 |
| Validate a JSON document, or up to 1000 of them, against a JSON Schema (draft 7, 2019-09 or 2020-12) and li... | `v0iddo/validate-json-schema` | $1.70 |
| Scrape job postings from elempleo.com, Colombia's second largest job board: title, company, city, salary ba... | `v0iddo/elempleo-scraper` | $0.85 |
| Scrape Rakuten Ichiba search results into product rows: title, JPY price, shop name, review score, review c... | `v0iddo/rakuten-japan-listings-scraper` | $1.28 |
| Scrape IT job offers from JustJoin.it in Poland: title, company, city, work mode, seniority, tech stack, sa... | `v0iddo/justjoin-it` | $0.50 |
| Scrape the Royal Caribbean fleet directory: every cruise ship with its class, name, description, image, and... | `v0iddo/royal-caribbean-scraper` | $1.19 |
| Sitemap URL extractor and sitemap index crawler. | `v0iddo/sitemap-url-extractor` | $1.00 |
| Scrape job listings from jobs.meinestadt.de: title, company, city, industry, employment type, salary range,... | `v0iddo/meinestadt-de-job-scraper` | $1.70 |
| Fetch MLB game scores from the official Stats API: game ID, teams, final score, R-H-E totals, inning-by-inn... | `v0iddo/mlb-daily-scoreboard-scraper` | $2.00 |
| Render an HTML snippet to a PNG, JPEG or WEBP image at any width, with retina scaling and transparent backg... | `v0iddo/html-to-image` | $1.70 |
| Turn text or a URL into a crisp QR code as PNG or SVG, with size and error-correction control. | `v0iddo/qr-code-generator` | $2.37 |
| Convert a date and time between IANA time zones with exact daylight-saving handling, inspect a zone's offse... | `v0iddo/time-zone-converter` | $1.00 |
| Scrape agency listings from sortlist.com service-category pages. | `v0iddo/sortlist-company-agency-scraper` | $1.27 |
| Scrape StubHub performer and category pages into event rows: event name, date, time, venue, city, location,... | `v0iddo/stubhub` | $2.55 |
| Scrape Talabat restaurant listings by country: restaurant ID, name, cuisines, category, logo and direct URL. | `v0iddo/talabat-scraper` | $1.00 |
| Scrape public posts from Truth Social accounts via the public REST API. | `v0iddo/truth-social-scraper` | $1.70 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/google-maps-scraper,v0iddo/website-content-crawler,v0iddo/similarweb-scraper,v0iddo/coles-scraper,v0iddo/audio-transcription,v0iddo/internshala-scraper,v0iddo/pdf-text-extractor,v0iddo/snapchat-scraper,v0iddo/video-frame-extractor,v0iddo/y-combinator-scraper`
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
