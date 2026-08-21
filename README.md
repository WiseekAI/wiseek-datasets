# Wiseek Filing Impact Monthly

Free, citable monthly statistics on how SEC filings move stocks, by AI importance
score (1 to 10), disclosure sentiment, filing family, and market cap. Produced by
[Wiseek](https://wiseek.ai/), which scores 14,000 to 27,000 SEC filings per month
in real time.

Canonical home and methodology: https://wiseek.ai/datasets/
Each release here is a byte-identical mirror of the canonical release page.
Verify with `manifest.sha256`.

## What's measured

Movement is the excess next-session move: the filing ticker's publication-price to
next-close move, minus the same-session close-to-close median of the filer panel
(all tickers with at least one SEC filing in the trailing 90 days and a real close
pair). This stops a broad market day from being credited to a filing. The wording
throughout is "moved after," not "caused by."

Each release ships aggregate tables covering all scores 1 to 10, plus
`events_score7plus.csv`: per-event rows (ticker, company, form, score, sentiment,
next-session result) for published filings scoring 7 or higher. That file
permanently archives the rolling 90-day
[Filing Impact Tracker](https://wiseek.ai/research/filing-impact-index/) export
before it forgets. Scores 1 to 6 appear only as aggregates.

## Files per release (`data/<release>/`)

| file | contents |
|---|---|
| `impact_by_score.csv` | score 1-10 vs excess-move distribution (T+1) |
| `score_x_mcap.csv` | score bucket by market-cap bucket |
| `score_x_sentiment.csv` | score bucket by sentiment, with direction hit-rate |
| `form_family.csv` | filing families (8-K, periodic, offering, insider, ownership, proxy) |
| `events_score7plus.csv` | per-event archive, score 7+ (pre-exclusion, pre-dedup) |
| `findings.json` | the release's pre-registered claims (max 3) and omissions |
| `meta.json` | counts, exclusions, filer-panel tape series, definitions, reproduction recipe |
| `manifest.sha256` | checksums; compare against the canonical release page |

Every stats column is withheld (`insufficient_sample`) when a cell has fewer than
30 measured filings. `pct_measured` discloses coverage per cell. Scores and
sentiment are point-in-time as stored at enrichment and never re-scored after
outcomes are known. Every aggregate cell reproduces exactly from the per-event
file; the recipe is in `meta.json`.

## License and citation

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Free for any use,
commercial included, with attribution. Cite as:

> Wiseek Filing Impact Monthly, YYYY-MM. Wiseek. https://wiseek.ai/datasets/YYYY-MM/

See `CITATION.cff`. First release: the launch note (2026-07-24 to 2026-08-14).
The first full monthly release (August 2026) lands in early September.

## More from Wiseek

- Product homepage: https://wiseek.ai/
- Plans and pricing: https://wiseek.ai/pricing/
- Dilution Risk Tracker (free tool): https://wiseek.ai/dilution-tracker/
- Stock Split Calendar (free tool): https://wiseek.ai/split-calendar/
- Live Filing Impact Tracker (rolling 90-day data): https://wiseek.ai/research/filing-impact-index/
- Scored market news: https://wiseek.ai/news/
- Ticker pages (about 6,800): https://wiseek.ai/ticker/
- Plain-English filing explainers: https://wiseek.ai/filings/
