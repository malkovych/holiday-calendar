# US Holiday Calendar (2026–2028)

Machine-readable US federal holidays, selected observances, and campaign dates for apps, cron jobs, and AI agents.

**[ThruMemory](https://thrumemory.com/)** · [World calendar](https://github.com/malkovych/world-holiday-calendar)

## Download

- [US calendar CSV](holidays-us-2026-2028.csv) — 78 dated records, UTF-8 with headers.
- [Agent quick reference](llms.txt)

## Integration

1. Parse dates as local calendar dates. The event's `market` is `US`. Select the actual IANA time zone from the recipient profile, for example `America/New_York`.
2. Prepare assets `prepare_days_before` calendar days before `start_date`. Send `send_days_before` calendar days before the event at `send_local_time`.
3. Only queue an activated campaign that matches audience preferences. Use a unique key containing occurrence, campaign, recipient, action, and channel. Treat `review` as a manual approval step and `off` as reference-only.

Example: US Thanksgiving 2027 is November 25. The separate Black Friday entry is intentionally covered by the world catalog, where global retail dates use market `WORLD`.

| Field | Meaning |
|---|---|
| `event_id` | Event or provider identifier |
| `occurrence_id` | Unique dated market-specific record |
| `start_date`, `end_date` | Inclusive ISO 8601 civil dates |
| `campaign_policy` | `targeted`, `review`, or `off` |
| `date_status` | Date provenance or estimation status |
| `source_url` | Source when available |

Coverage focuses on federal calendar dates and selected observances. State holidays and substitute workdays are partial. Multiple records on one date can refer to the same occasion. Verify dates for official closure decisions.

Sources: [Python Holidays](https://holidays.readthedocs.io/en/latest/) and the cited sources in the CSV.
