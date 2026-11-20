# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- High-Impact CVE Watchdog GitHub Actions workflow (`.github/workflows/cisa-kev-high-epss-check.yml`) monitoring the [CISA KEV](https://www.cisa.gov/known-exploited-vulnerabilities-catalog) catalog, enriching alerts with [FIRST.org EPSS](https://www.first.org/epss/) scores, deduplicating previously reported CVEs, and opening GitHub Issues for newly detected vulnerabilities.
- Standard project documentation and contribution files: `README.md`, `CONTRIBUTING.md`, and `CHANGELOG.md`.
- Initial `.gitignore` configuration for IntelliJ IDEA.
