---
license: cc-by-4.0
pretty_name: Wiseek Filing Impact Monthly
language:
  - en
tags:
  - finance
  - sec-filings
  - event-study
  - stock-market
  - time-series
size_categories:
  - 1K<n<10K
---

# Wiseek Filing Impact Monthly

Does an 8-K actually move the stock? [Wiseek](https://wiseek.ai) scores 14,000 to
27,000 SEC filings a month for importance (1 to 10) and sentiment, in real time,
across about 6,800 US tickers. This dataset records what happened next: each filing
ticker's next-session price move, measured as excess over the same-session median
move of all actively filing tickers, so a broad market day is not credited to any
single filing.

Canonical home and methodology: https://wiseek.ai/datasets/
Checksummed GitHub mirror: https://github.com/WiseekAI/wiseek-datasets
License: CC BY 4.0. Free for any use, commercial included, with attribution and a
link to the release page you used.

## Files per release (`data/<release>/`)

| file | contents |
|---|---|
| `impact_by_score.csv` | score 1-10 vs excess-move distribution (T+1) |
| `score_x_mcap.csv` | score bucket by market-cap bucket |
| `score_x_sentiment.csv` | score bucket by sentiment, with direction hit-rate |
| `form_family.csv` | filing families (current-report, periodic, offering, insider, ownership, proxy) |
| `events_score7plus.csv` | per-event archive, score 7+ (pre-exclusion, pre-dedup) |
| `findings.json` / `meta.json` | pre-registered claims, methodology, provenance, reproduction recipe |
| `manifest.sha256` | checksums; compare against the canonical release page |

Every aggregate cell reproduces exactly from the per-event file. The recipe is in
`meta.json`. Cells with fewer than 30 measured filings have their statistics
withheld. Scores are point-in-time as stored at enrichment and never re-scored
after outcomes are known. The wording throughout is "moved after," not "caused by."

## What the launch window showed

Between 2026-07-24 and 2026-08-14, 11,416 filings had a clean next-session
measurement. Filings Wiseek scored 9 or 10 moved a median 4.99% (excess) by the
next close. Filings scored 1 to 4 moved 2.14%. The gap held in every market-cap
band.

## Citation

> Wiseek Filing Impact Monthly, {release}. Wiseek. https://wiseek.ai/datasets/{release}/

## More from Wiseek

- Product homepage: https://wiseek.ai/
- Plans and pricing: https://wiseek.ai/pricing/
- Dilution Risk Tracker (free tool): https://wiseek.ai/dilution-tracker/
- Stock Split Calendar (free tool): https://wiseek.ai/split-calendar/
- Live Filing Impact Tracker (rolling 90-day data): https://wiseek.ai/research/filing-impact-index/
- Scored market news: https://wiseek.ai/news/
- Ticker pages (about 6,800): https://wiseek.ai/ticker/
- Plain-English filing explainers: https://wiseek.ai/filings/
