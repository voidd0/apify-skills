# vøiddo Apify skills

Agent skills for Claude Code, Codex, Copilot, Cursor and any agent that reads `SKILL.md`. Each skill turns a data
request ("export these careers pages to CSV", "top iPhone apps in Germany", "screen these names against OFAC") into a
run of the right Actor on the Apify Store, with the input schema fetched, the cost sized before the run and the rows
checked before delivery. 0 Actors in 0 skills, all pay per result.

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


The list of every Actor with prices and example code: [voidd0/apify-actors](https://github.com/voidd0/apify-actors).

## Disclosure

The Actors these skills route to are built and maintained by vøiddo (Apify Store developer `v0iddo`). No referral or
tracking parameters are used. This repository is rebuilt every day from the live Store pages.

MIT for everything in this repository. Made by [vøiddo](https://voiddo.com).
