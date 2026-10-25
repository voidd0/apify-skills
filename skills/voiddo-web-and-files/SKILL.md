---
name: voiddo-web-and-files
description: "Turn web pages and files into data: crawl a site to clean text, screenshot or render pages to PDF or images, extract PDF text, convert images, transcribe audio, extract video frames, download files in bulk, read sitemaps, audit SEO and detect a site's technology. Routes to 12 pay-per-result Apify Actors by vøiddo. Use when the user asks to crawl a website for its text, take website screenshots, convert HTML to PDF, extract text from PDFs, transcribe a podcast episode, list a site's URLs from its sitemap, run an SEO audit."
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

       apify actors info "v0iddo/website-content-crawler" --input --json --user-agent voiddo-skills/voiddo-web-and-files 2>/dev/null

3. Size the run before it starts: cost is about rows x price per 1,000 / 1,000. Set the row cap
   (`maxItems` on most of these Actors) and tell the user the estimate when it is over $1.
4. Run the Actor and read the rows:

       apify actors call "v0iddo/website-content-crawler" -i '{"startUrls": ["https://docs.python.org/3/library/"], "maxDepth": 1, "maxPagesPerUrl": 15, "maxItems": 20}' --json --user-agent voiddo-skills/voiddo-web-and-files 2>/dev/null

5. Check before you deliver: the row count, empty columns, and rows whose fields say an item failed (several
   Actors return one row per input that could not be read, with the reason). Report what was asked, what came back
   and what is missing.

## Actor routing

| User need | Actor ID | Per 1,000 results |
| --- | --- | --- |
| Crawls any public website from a start URL, follows internal links up to a set depth, and extracts title, b... | `v0iddo/website-content-crawler` | $5.05 |
| Extract the text of PDF files page by page, as plain text or as Markdown with headings, bold, lists and par... | `v0iddo/pdf-text-extractor` | $1.00 |
| Speech to text with Whisper: transcribe audio and video files and podcast episodes, with timestamps and SRT... | `v0iddo/audio-transcription` | $10.00 |
| Extract still frames from video files as JPEG, PNG or WebP images with timecodes: one every N seconds, a nu... | `v0iddo/video-frame-extractor` | $1.50 |
| Audit the on-page SEO of any public web pages: title, meta description, headings, canonical, indexability,... | `v0iddo/seo-audit` | $4.00 |
| Download files in bulk from direct links, or every image, video, audio file, PDF, document or archive on a... | `v0iddo/bulk-file-downloader` | $2.00 |
| Convert and resize images between PNG, JPEG, WEBP, GIF, BMP, TIFF and ICO, with quality, fit modes, transpa... | `v0iddo/image-converter` | $1.00 |
| Capture a public web page as a PNG, JPEG or WEBP image: any viewport size, full page, retina scaling, optio... | `v0iddo/url-screenshot` | $4.25 |
| Turn an HTML document into a print-ready PDF with page size, margins, orientation and page-numbered header... | `v0iddo/html-to-pdf` | $6.88 |
| Render an HTML snippet to a PNG, JPEG or WEBP image at any width, with retina scaling and transparent backg... | `v0iddo/html-to-image` | $4.25 |
| Sitemap URL extractor and sitemap index crawler. | `v0iddo/sitemap-url-extractor` | $1.00 |
| Turn text or a URL into a crisp QR code as PNG or SVG, with size and error-correction control. | `v0iddo/qr-code-generator` | $1.70 |

## Other ways to call them

- Apify MCP server, only these Actors as tools: `https://mcp.apify.com/?actors=v0iddo/website-content-crawler,v0iddo/pdf-text-extractor,v0iddo/audio-transcription,v0iddo/video-frame-extractor,v0iddo/seo-audit,v0iddo/bulk-file-downloader,v0iddo/image-converter,v0iddo/url-screenshot,v0iddo/html-to-pdf,v0iddo/html-to-image`
- One HTTP request, any language (returns the JSON rows):

      curl -X POST "https://api.apify.com/v2/acts/v0iddo~website-content-crawler/run-sync-get-dataset-items" \
        -H "Authorization: Bearer $APIFY_TOKEN" -H 'Content-Type: application/json' -d '{"startUrls": ["https://docs.python.org/3/library/"], "maxDepth": 1, "maxPagesPerUrl": 15, "maxItems": 20}'

## Troubleshooting

- 0 rows: the input does not match the site (a wrong link, slug or country); compare it with the example in the
  index, then run again with a small cap.
- A site refused the run or showed a check page: the run's status message says so. Run again later or with fewer
  items; the Actors never bypass logins or captchas.
- Run stopped at the cap: raise the row cap or the run's maximum charge; you pay only for rows returned.
- Unknown field in the input: fetch the schema again (step 2); fields change between versions.
