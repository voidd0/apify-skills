# vøiddo Apify skills

Agent skills for Claude Code, Codex, Copilot, Cursor and any agent that reads `SKILL.md`. Each skill turns a data
request ("export these careers pages to CSV", "top iPhone apps in Germany", "screen these names against OFAC") into a
run of the right Actor on the Apify Store, with the input schema fetched, the cost sized before the run and the rows
checked before delivery. 38 Actors in 9 skills, all pay per result.

## Install

```bash
npx skills add voidd0/apify-skills
```

Claude Code plugin marketplace:

```text
/plugin marketplace add voidd0/apify-skills
```

Or copy a folder from `skills/` into your agent's skills directory. You need an Apify account and an API token from
[Console > Settings > Integrations](https://console.apify.com/settings/integrations) (`APIFY_TOKEN`, or `apify login`).

## Skills

| Skill | Covers | Actors |
| --- | --- | --- |
| [`voiddo-job-postings`](skills/voiddo-job-postings/SKILL.md) | Job postings from careers pages and job boards | 3 |
| [`voiddo-ecommerce-products`](skills/voiddo-ecommerce-products/SKILL.md) | Products, prices and sales signals from marketplaces | 1 |
| [`voiddo-app-store-data`](skills/voiddo-app-store-data/SKILL.md) | App stores and extension marketplaces | 10 |
| [`voiddo-public-records`](skills/voiddo-public-records/SKILL.md) | Government and regulatory records | 10 |
| [`voiddo-market-data`](skills/voiddo-market-data/SKILL.md) | Stock quotes, exchange rates and crypto market data | 3 |
| [`voiddo-developer-data`](skills/voiddo-developer-data/SKILL.md) | Packages, repositories and vulnerabilities | 5 |
| [`voiddo-research-and-news`](skills/voiddo-research-and-news/SKILL.md) | Papers, articles, newsletters and podcasts | 4 |
| [`voiddo-events`](skills/voiddo-events/SKILL.md) | Events by place and topic | 1 |
| [`voiddo-web-and-files`](skills/voiddo-web-and-files/SKILL.md) | Web pages, documents and media files | 1 |

The list of every Actor with prices and example code: [voidd0/apify-actors](https://github.com/voidd0/apify-actors).

## Disclosure

The Actors these skills route to are built and maintained by vøiddo (Apify Store developer `v0iddo`). No referral or
tracking parameters are used. This repository is rebuilt every day from the live Store pages.

MIT for everything in this repository. Made by [vøiddo](https://voiddo.com).
