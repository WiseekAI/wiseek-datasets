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

**Do SEC filings move stocks?** Monthly statistics from [Wiseek](https://wiseek.ai),
which scores 14,000–27,000 SEC filings per month for importance (1–10) and sentiment
in real time: score & sentiment vs next-session **excess** price moves (market-day
effect subtracted via a filer-panel tape median), split by filing family and
market-cap bucket — plus a per-event archive (ticker, company, form, score,
sentiment, next-session result) for published filings scoring ≥7.

- **Canonical home & methodology:** https://wiseek.ai/datasets/
- **GitHub mirror (checksummed):** https://github.com/WiseekAI/wiseek-datasets
- **License:** CC BY 4.0 — free for any use with attribution + a link to the release page used.

## Files per release (`data/<release>/`)

| file | contents |
|---|---|
| `impact_by_score.csv` | score 1–10 × excess-move distribution (T+1) |
| `score_x_mcap.csv` | score bucket × market-cap bucket |
| `score_x_sentiment.csv` | score bucket × sentiment, incl. direction hit-rate |
| `form_family.csv` | filing families (current-report, periodic, offering, insider…) |
| `events_score7plus.csv` | per-event archive, score ≥7 (pre-exclusion, pre-dedup) |
| `findings.json` / `meta.json` | pre-registered claims + methodology, provenance, reproduction recipe |
| `manifest.sha256` | checksums (match against the canonical release page) |

Every aggregate cell reproduces exactly from the per-event file — the recipe is in
`meta.json`. Cells under n=30 have statistics withheld. Scores are point-in-time
(never re-scored after outcomes are known). All language is "moved after," never
"caused by."

## Headline finding (launch window, Jul 24 – Aug 14, 2026; 11,416 measured filings)

Filings Wiseek scored **9–10** moved a median **4.99%** (excess of the filer-panel
tape) by the next close, vs **2.14%** for scores 1–4 — consistent across every
market-cap band.

## Citation

> Wiseek Filing Impact Monthly, {release}. Wiseek. https://wiseek.ai/datasets/{release}/
