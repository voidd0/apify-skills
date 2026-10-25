# Web pages, documents and media files: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Website Content Crawler: Pages to Clean Text

- Actor ID: `v0iddo/website-content-crawler`
- Store page: https://apify.com/v0iddo/website-content-crawler
- Price: $5.05 per 1,000 results, nothing per run

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

## PDF Text Extractor: Markdown & Metadata

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

## Audio Transcription: Speech to Text, Video, Podcast

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

## Video Frame Extractor: Scenes, Thumbnails

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

## Bulk File and Image Downloader: Pages, Links

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

## Image Converter (PNG, JPEG, WEBP, GIF and more)

- Actor ID: `v0iddo/image-converter`
- Store page: https://apify.com/v0iddo/image-converter
- Price: $1.00 per 1,000 results, nothing per run

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

## Website Screenshot Generator: URL to PNG, JPEG or WEBP

- Actor ID: `v0iddo/url-screenshot`
- Store page: https://apify.com/v0iddo/url-screenshot
- Price: $4.25 per 1,000 results, nothing per run

Capture a public web page as a PNG, JPEG or WEBP image: any viewport size, full page, retina scaling, optional cookie-banner hiding.

Example input:

```json
{
  "url": "https://example.com"
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## HTML to PDF (A4, Letter, Legal, A3 and more)

- Actor ID: `v0iddo/html-to-pdf`
- Store page: https://apify.com/v0iddo/html-to-pdf
- Price: $6.88 per 1,000 results, nothing per run

Turn an HTML document into a print-ready PDF with page size, margins, orientation and page-numbered header and footer.

Example input:

```json
{
  "html": "<h1>Invoice #1042</h1><p>Total due: 120.00 USD, payable within 14 days.</p>"
}
```

Output fields: `index`, `file_url`, `filename`, `mime`, `bytes`, `credits`, `ms`

## HTML to Image (PNG, JPEG and WEBP)

- Actor ID: `v0iddo/html-to-image`
- Store page: https://apify.com/v0iddo/html-to-image
- Price: $4.25 per 1,000 results, nothing per run

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
