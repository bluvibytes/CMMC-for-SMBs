# Changelog

All notable changes to this tool are recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project aims to follow [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Validation run on each release: extract the script and run a Node syntax check, confirm zero em dashes, confirm the Content-Security-Policy is present, and audit every outbound link against its authoritative source.

## [1.1.0] - 2026-06-09

### Changed
- Reworked the top progress indicator. Red no longer appears in the bar. It is now a single calm fill on a neutral track, so it reads as how far through the checklist you are, not as a pass or fail score. Red is reserved for an objective you deliberately mark Not met.
- Progress now tracks all 59 assessment objectives, so the bar moves with every mark rather than only when a full practice closes.
- The status headline reads "X of 59 objectives met" with a percent complete. Whether you are actually ready to attest stays in the readiness summary, where a real problem should announce itself.
- Standardized the finding labels across every export (PDF SSP, Word SSP, CSV, gap report, and text SSP) onto one set: MET, NOT MET, N/A, and MET (evidence incomplete). The on-screen status chips and the compare view keep their shorter labels on purpose, so there is one formal register for documents that leave the building and one friendly register on screen.
- Rebuilt the text SSP (Copy SSP as text) to match the Word and PDF versions: the same four sections (System Identification and Scope, Control Implementation, Gaps, Affirmation), the disclaimer line, and an affirmation block, and removed the DRAFT label.

### Added
- Each assessment objective now shows its official identifier above the objective text, for example `AC.L1-3.1.1[b]`, matching how the DoD Level 1 Assessment Guide and an assessor cite it. This keeps context when you are scrolled deep into a control.
- "May also help cover" notes in the documentation guidance, flagging where one piece of evidence supports more than one practice (identity, malicious code protection, physical access).

### Fixed
- Corrected the repository link in the footer to the lowercase repository path.

## [1.0.0] - 2026-06-07

### Added
- Initial public release. A free, open source, offline, single file CMMC Level 1 self-assessment for small and mid-sized businesses.
- Covers the 15 safeguarding requirements of FAR 52.204-21, expressed as 17 practices and 59 assessment objectives, each with plain-language guidance, an evidence suggestion, and a fix-it path.
- Scope step for recording the FCI or CUI determination and mapping the data footprint before requesting a quote.
- Local exports: a System Security Plan in Word and print-to-PDF form, including a gaps-to-close section, plus a CSV for tracking. Everything is generated in the browser.
- No network calls (Content-Security-Policy locked to `connect-src 'none'`), no browser storage, and no data collection. Authoritative .gov, NIST, and CFR sources throughout.
- A content fingerprint on the exported plan so a recipient can tell whether the contents were altered.

[1.1.0]: https://github.com/bluvibytes/cmmc-for-smbs/releases/tag/v1.1.0
[1.0.0]: https://github.com/bluvibytes/cmmc-for-smbs/releases/tag/v1.0.0
