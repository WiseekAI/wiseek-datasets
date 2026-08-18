# Wiseek Filing Impact Monthly

Free, citable monthly statistics on **how SEC filings actually move stocks** — by AI
importance score (1–10), disclosure sentiment, filing family, and market cap.
Produced by [Wiseek](https://wiseek.ai/), which scores 14,000–27,000 SEC filings per
month in real time.

**Canonical home & methodology:** https://wiseek.ai/datasets/
Each release here is a byte-identical mirror of the canonical release page
(verify with `manifest.sha256`).

## What's measured

Movement is the **excess next-session move**: the filing ticker's publication-price →
next-close move, minus the same-session close-to-close median of the *filer panel*
(all tickers with ≥1 SEC filing in the trailing 90 days and a real close pair). This
stops a broad market day from masquerading as filing impact. All language is
"moved after", never "caused by".

Aggregates only — no per-filing rows, no tickers. For per-event data see the rolling
90-day [Filing Impact Tracker](https://wiseek.ai/research/filing-impact-index/);
each monthly release permanently archives what that rolling window forgets.

## Files per release (`data/YYYY-MM/`)

| file | contents |
|---|---|
| `impact_by_score.csv` | score 1–10 × excess-move distribution (T+1) |
| `score_x_mcap.csv` | score bucket × market-cap bucket |
| `score_x_sentiment.csv` | score bucket × sentiment, incl. direction hit-rate |
| `form_family.csv` | 8-K/periodic/offering/insider/ownership/proxy families |
| `cum_t5_by_score.csv` | cumulative move through 5th session (contains T+1; raw) |
| `findings.json` | the release's pre-registered claims (max 3) + omissions |
| `meta.json` | counts, exclusions, filer-panel tape series, definitions |
| `manifest.sha256` | checksums (match against the canonical release page) |

Column dictionary: every stats column is withheld (`insufficient_sample`) when a
cell has fewer than 30 measured filings. `pct_measured` discloses coverage per cell.
Scores/sentiment are point-in-time as stored at enrichment — never re-scored after
outcomes are known.

## License & citation

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free for any use with
attribution. Cite as:

> Wiseek Filing Impact Monthly, YYYY-MM. Wiseek. https://wiseek.ai/datasets/YYYY-MM/

See `CITATION.cff`. First release: **2026-08** (published early September 2026).
