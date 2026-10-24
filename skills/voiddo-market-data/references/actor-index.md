# Stock quotes, exchange rates and crypto market data: Actor index

Every Actor below is public on the Apify Store. The example input is the one on its Store page, run every day by Apify's own test; output fields are the Actor's overview columns.

## Yahoo Finance Scraper: Stock Quotes and Key Statistics

- Actor ID: `v0iddo/mint-yahoo-finance-scraper`
- Store page: https://apify.com/v0iddo/mint-yahoo-finance-scraper
- Price: $1.00 per 1,000 results, nothing per run

Scrape Yahoo Finance quotes and key statistics for stocks, ETFs, indexes, crypto, currencies and futures: price, change, volume, market cap, P/E, EPS, dividend, 52 week range, analyst target, sector and next earnings date.

Example input:

```json
{
  "tickers": [
    "AAPL",
    "MSFT",
    "NVDA",
    "AMZN",
    "GOOGL",
    "META",
    "TSLA",
    "SPY",
    "QQQ",
    "^GSPC",
    "BTC-USD",
    "EURUSD=X"
  ],
  "maxItems": 20
}
```

Output fields: `symbol`, `name`, `quoteType`, `price`, `currency`, `changePercent`, `volume`, `marketCap`, `trailingPE`, `dividendYield`, `fiftyTwoWeekLow`, `fiftyTwoWeekHigh`, `regularMarketTime`, `url`

## CoinGecko Scraper: Crypto Market Data by Category

- Actor ID: `v0iddo/coingecko-category-snapshot`
- Store page: https://apify.com/v0iddo/coingecko-category-snapshot
- Price: $0.10 per 1,000 results, nothing per run

For each CoinGecko category ID (`layer-1`, `defi`, `meme-token`, etc.), pull its coins by market cap: 250 per category by default, more if you raise the cap.

Example input:

```json
{
  "categories": [
    "layer-1",
    "meme-token"
  ],
  "maxCoinsPerCategory": 20
}
```

Output fields: `category`, `vsCurrency`, `snapshotAt`, `id`, `symbol`, `name`, `image`, `currentPrice`, `marketCap`, `marketCapRank`, `fdv`, `totalVolume`

## Currency Exchange Rates (ECB)

- Actor ID: `v0iddo/mint-currency-exchange-rates`
- Store page: https://apify.com/v0iddo/mint-currency-exchange-rates
- Price: $3.40 per 1,000 results, nothing per run

Latest and historical euro foreign exchange reference rates from the European Central Bank, with conversion between any two of its currencies.

Example input:

```json
{
  "op": "convert",
  "amount": "100",
  "from": "EUR",
  "to": "USD",
  "date": "2026-01-02"
}
```

Output fields: `index`, `amount`, `from`, `to`, `rate`, `result`, `date_used`, `source`

## CoinGecko Tokens Scraper: Token List by Category

- Actor ID: `v0iddo/coingecko-tokens-by-category`
- Store page: https://apify.com/v0iddo/coingecko-tokens-by-category
- Price: $1.00 per 1,000 results, nothing per run

Pulls the top 100 tokens by market cap in each CoinGecko category (DeFi, meme, L1, ecosystem tags) with current price, market cap, 24h volume, rank, and price change.

Example input:

```json
{
  "category": [
    "layer-1",
    "meme-token",
    "gaming"
  ]
}
```

Output fields: `category`, `coin_id`, `symbol`, `name`, `price_usd`, `market_cap_usd`, `rank`, `volume_24h_usd`, `change_pct_24h`, `circulating_supply`, `all_time_high_usd`, `logo_url`

## DefiLlama Scraper: Protocol TVL by Chain and Category

- Actor ID: `v0iddo/defillama-protocols-snapshot`
- Store page: https://apify.com/v0iddo/defillama-protocols-snapshot
- Price: $0.10 per 1,000 results, nothing per run

Snapshot every DefiLlama-tracked protocol filtered by chain, category, and TVL range.

Example input:

```json
{
  "chains": [
    "Ethereum"
  ]
}
```

Output fields: `snapshotAt`, `id`, `slug`, `name`, `symbol`, `category`, `chain`, `allChains`, `url`, `description`, `logo`, `audits`
