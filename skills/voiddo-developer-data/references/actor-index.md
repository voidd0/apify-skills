# Packages, repositories and vulnerabilities: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Hacker News Scraper: Stories and Comments by Query

- Actor ID: `v0iddo/hn-algolia-search`
- Store page: https://apify.com/v0iddo/hn-algolia-search
- Price: $0.10 per 1,000 results, nothing per run

Search Hacker News via the public Algolia API.

Example input:

```json
{
  "queries": [
    "Show HN: open source"
  ],
  "maxResultsPerQuery": 20
}
```

Output fields: `objectID`, `storyId`, `title`, `author`, `url`, `points`, `numComments`, `createdAt`, `createdAtUnix`, `tags`, `commentText`, `permalink`

## PyPI Scraper: Python Package Details and Stats

- Actor ID: `v0iddo/pypi-package-tracker`
- Store page: https://apify.com/v0iddo/pypi-package-tracker
- Price: $0.20 per 1,000 results, nothing per run

Snapshot PyPI package metadata using the public pypi.org/pypi/<pkg>/json endpoint.

Example input:

```json
{
  "packages": [
    "requests",
    "numpy",
    "pandas"
  ]
}
```

Output fields: `snapshotAt`, `name`, `latestVersion`, `summary`, `author`, `license`, `homepage`, `projectUrls`, `requiresPython`, `classifiers`, `keywords`, `releaseCount`

## GitHub Security Advisories Scraper by Ecosystem

- Actor ID: `v0iddo/github-security-advisories`
- Store page: https://apify.com/v0iddo/github-security-advisories
- Price: $0.50 per 1,000 results, nothing per run

For each ecosystem (NPM, PIP, MAVEN, NUGET, RUBYGEMS, RUST, GO, ACTIONS, SWIFT and more), pull recent GitHub Security Advisories.

Example input:

```json
{
  "ecosystems": [
    "NPM",
    "PIP"
  ],
  "maxResults": 20
}
```

Output fields: `ghsaId`, `summary`, `description`, `severity`, `classification`, `publishedAt`, `updatedAt`, `withdrawnAt`, `url`, `cves`, `references`, `cwes`

## npm Package Stats Scraper: Metadata and Downloads

- Actor ID: `v0iddo/npm-package-tracker`
- Store page: https://apify.com/v0iddo/npm-package-tracker
- Price: $0.20 per 1,000 results, nothing per run

Snapshot npm package stats from the public registry and downloads APIs.

Example input:

```json
{
  "packages": [
    "react",
    "next",
    "vue",
    "svelte"
  ]
}
```

Output fields: `snapshotAt`, `name`, `description`, `latestVersion`, `createdAt`, `modifiedAt`, `license`, `homepage`, `repositoryUrl`, `maintainers`, `keywords`, `dependenciesCount`

## NVD CVE Scraper: Vulnerabilities by Vendor and Severity

- Actor ID: `v0iddo/nvd-cve-tracker`
- Store page: https://apify.com/v0iddo/nvd-cve-tracker
- Price: $2.00 per 1,000 results, nothing per run

Pull new/modified CVEs from NIST NVD.

Example input:

```json
{
  "maxResultsPerQuery": 20
}
```

Output fields: `cveId`, `published`, `lastModified`, `vulnStatus`, `description`, `cvssV3Version`, `cvssV3BaseScore`, `cvssV3Severity`, `cvssV3VectorString`, `exploitabilityScore`, `impactScore`, `cvssV4BaseScore`
