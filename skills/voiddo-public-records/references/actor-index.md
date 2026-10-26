# Government and regulatory records: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## ClinicalTrials.gov Scraper: Trial Updates by Query

- Actor ID: `v0iddo/clinicaltrials-updates-tracker`
- Store page: https://apify.com/v0iddo/clinicaltrials-updates-tracker
- Price: $2.98 per 1,000 results, nothing per run

Pull recently-updated ClinicalTrials.gov studies matching a query.

Example input:

```json
{
  "queries": [
    "lung cancer"
  ],
  "maxResultsPerQuery": 20
}
```

Output fields: `nctId`, `briefTitle`, `officialTitle`, `overallStatus`, `phases`, `studyType`, `leadSponsor`, `collaborators`, `conditions`, `keywords`, `interventions`, `startDate`

## USAspending Awards Scraper: Federal Contracts and Grants

- Actor ID: `v0iddo/usaspending-federal-awards`
- Store page: https://apify.com/v0iddo/usaspending-federal-awards
- Price: $1.70 per 1,000 results, nothing per run

Pull recent federal contract and grant awards from USAspending.gov.

Example input:

```json
{
  "maxResults": 20
}
```

Output fields: `awardId`, `internalId`, `detailUrl`, `recipientName`, `recipientUei`, `awardAmount`, `description`, `awardingAgency`, `awardingSubAgency`, `actionDate`, `startDate`, `endDate`

## Federal Register Scraper: Rules, Proposed Rules, Notices

- Actor ID: `v0iddo/federal-register-tracker`
- Store page: https://apify.com/v0iddo/federal-register-tracker
- Price: $0.10 per 1,000 results, nothing per run

Pull Federal Register articles filtered by agency, document type, date range, significant-rule flag, or full-text query.

Example input:

```json
{
  "maxResults": 20
}
```

Output fields: `snapshotAt`, `documentNumber`, `title`, `type`, `subtype`, `action`, `abstract`, `publicationDate`, `signingDate`, `effectiveOn`, `commentsCloseOn`, `agencies`

## NIH RePORTER Scraper: Research Grants by Query

- Actor ID: `v0iddo/nih-reporter-grants`
- Store page: https://apify.com/v0iddo/nih-reporter-grants
- Price: $3.00 per 1,000 results, nothing per run

Pull recent NIH research grants from RePORTER.

Example input:

```json
{
  "maxResults": 20
}
```

Output fields: `applId`, `projectNum`, `projectTitle`, `fiscalYear`, `activityCode`, `awardType`, `awardAmount`, `isActive`, `projectStartDate`, `projectEndDate`, `organizationName`, `organizationCity`

## SEC 8-K Scraper: Material Events by Ticker

- Actor ID: `v0iddo/sec-8k-material-events-tracker`
- Store page: https://apify.com/v0iddo/sec-8k-material-events-tracker
- Price: $10.00 per 1,000 results, nothing per run

Pull recent SEC 8-K filings (Current Reports) by stock ticker.

Example input:

```json
{
  "tickers": [
    "TSLA",
    "JPM"
  ]
}
```

Output fields: `ticker`, `companyCik`, `companyName`, `filingDate`, `reportDate`, `accessionNumber`, `items`, `itemSummaries`, `primaryDocument`, `filingUrl`, `indexUrl`

## Insider Trades Scraper: SEC EDGAR Form 4 by Ticker

- Actor ID: `v0iddo/sec-form4-insider-trades`
- Store page: https://apify.com/v0iddo/sec-form4-insider-trades
- Price: $2.32 per 1,000 results, nothing per run

Pull clean, parsed Form 4 insider trades from SEC EDGAR by ticker.

Example input:

```json
{
  "tickers": [
    "AAPL",
    "META"
  ]
}
```

Output fields: `ticker`, `companyCik`, `companyName`, `insiderName`, `insiderCik`, `insiderRoles`, `officerTitle`, `accessionNumber`, `filingDate`, `periodOfReport`, `filingUrl`, `xmlUrl`

## SEC 13F Scraper: Institutional Holdings by Filer

- Actor ID: `v0iddo/sec-13f-institutional-holdings`
- Store page: https://apify.com/v0iddo/sec-13f-institutional-holdings
- Price: $1.53 per 1,000 results, nothing per run

Pull SEC Form 13F quarterly holdings for any institutional manager by CIK.

Example input:

```json
{
  "filerCiks": [
    "1067983"
  ]
}
```

Output fields: `filerCik`, `filerName`, `filingManager`, `form`, `accessionNumber`, `filingDate`, `periodOfReport`, `isAmendment`, `nameOfIssuer`, `titleOfClass`, `cusip`, `valueUsd`

## openFDA Drug Recalls Scraper: Enforcement Reports

- Actor ID: `v0iddo/openfda-drug-recalls`
- Store page: https://apify.com/v0iddo/openfda-drug-recalls
- Price: $5.00 per 1,000 results, nothing per run

Pull recent FDA drug recall actions.

Example input:

```json
{
  "maxResults": 20
}
```

Output fields: `recallNumber`, `eventId`, `status`, `classification`, `productType`, `recallingFirm`, `firmAddress`, `productDescription`, `productQuantity`, `reasonForRecall`, `voluntaryMandated`, `initialFirmNotification`

## SEC 13D/13G Beneficial Ownership Filings Scraper

- Actor ID: `v0iddo/sec-13d-13g-beneficial-ownership`
- Store page: https://apify.com/v0iddo/sec-13d-13g-beneficial-ownership
- Price: $4.89 per 1,000 results, nothing per run

Scrape SEC EDGAR 13D and 13G beneficial ownership filings by company CIK.

Example input:

```json
{
  "cik": [
    "0000320193",
    "0001318605",
    "0001067983"
  ]
}
```

Output fields: `cik`, `company_name`, `accession_number`, `form`, `filing_date`, `report_date`, `primary_document`, `primary_doc_description`

## FCC ECFS Public Notices & Filings Scraper

- Actor ID: `v0iddo/fcc-public-notices`
- Store page: https://apify.com/v0iddo/fcc-public-notices
- Price: $2.55 per 1,000 results, nothing per run

Scrapes FCC ECFS (Electronic Comment Filing System) filings and public notices by docket/proceeding number.

Example input:

```json
{
  "proceeding": [
    "17-108",
    "21-450",
    "23-65"
  ]
}
```

Output fields: `snapshotAt`, `filing_id`, `date_received`, `submission_type`, `filer_name`, `proceeding`, `document_filename`, `document_url`, `city`, `state`, `text_snippet`
