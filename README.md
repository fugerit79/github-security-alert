# GitHub Security Alert

Automated security watchdog powered by GitHub Actions that monitors newly added vulnerabilities in the [CISA Known Exploited Vulnerabilities (KEV)](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) catalog, enriches them with [FIRST.org EPSS](https://www.first.org/epss/) exploitation probability scores, and opens actionable GitHub Issues.

## How It Works

The workflow [`.github/workflows/cisa-kev-high-epss-check.yml`](.github/workflows/cisa-kev-high-epss-check.yml) (`High-Impact CVE Watchdog`) runs automatically every day at **07:00 UTC**:

1. **CISA KEV Fetch:** Downloads the official CISA KEV JSON feed and filters vulnerabilities added within the configured lookback window (default: **last 2 days** / 48 hours).
2. **EPSS Enrichment:** Queries the public FIRST.org EPSS API to attach exploitation probability and percentile metrics to each detected CVE (non-blocking if the EPSS API is temporarily unavailable).
3. **Deduplication:** Inspects recent repository issues labeled `security` (open or closed) so that CVEs already reported in previous runs are not duplicated.
4. **Alerting:** Writes a formatted report to the GitHub Actions Step Summary and opens a GitHub Issue labeled `security` and `urgent` containing NVD links, vendor/product metadata, CISA due dates, ransomware flags, EPSS scores, and required remediation actions.

## Manual Execution

You can trigger the workflow manually from the **Actions** tab (`High-Impact CVE Watchdog` → **Run workflow**) with optional inputs:

| Input | Default | Description |
| :--- | :--- | :--- |
| `lookback_days` | `2` | Number of days (`1`–`365`) to look back in the CISA KEV catalog. |
| `dry_run` | `false` | When `true`, runs detection, EPSS enrichment, and step summary without creating a GitHub Issue. |

## Permissions & Security

- Top-level `permissions: {}` with job-scoped least privilege (`issues: write`).
- Third-party actions pinned to full commit SHAs (`actions/github-script@v9.0.0`).
- Workflow inputs passed exclusively via environment variables (`env:`) to prevent script injection.
- Single-flight concurrency group (`cisa-kev-high-epss-check`) to avoid race-condition duplicate alerts.

## Contributing & Changelog

- Contribution guidelines and Generative AI policy: [CONTRIBUTING.md](CONTRIBUTING.md)
- Release history and notable changes: [CHANGELOG.md](CHANGELOG.md)
