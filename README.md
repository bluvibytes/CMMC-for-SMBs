# CMMC for SMBs: Level 1 Self-Assessment Tool

A free, offline, open-source tool that walks a small or medium-sized business through a CMMC Level 1 self-assessment in plain English. It runs entirely in your browser from a single file, collects no data, and makes no network calls. It is built and maintained by [BluVi LLC](https://bluvi.ai).

**Use it here:** open `index.html` in any modern browser, or visit the hosted version if one is published for this repository.

---

## Why this exists

Small defense contractors are routinely overcharged for CMMC work that they can understand and, at Level 1, largely do themselves. The goal of this tool is to lower that cost by explaining what Level 1 actually requires, in language a business owner can follow, so you walk into any conversation with a consultant or assessor already knowing the lay of the land.

This is not anti-consultant. Good help is worth paying for. It is anti-overcharge. Use this before or alongside paid support so you are not paying for scope you do not have, or for an explanation you could have read for free.

## What CMMC Level 1 is, briefly

Level 1 covers the 15 basic safeguarding requirements in FAR 52.204-21, which the rule grades as 59 yes-or-no assessment objectives across 17 practices. It applies to companies that handle Federal Contract Information (FCI) and nothing more sensitive. You assess yourself once a year and a senior official affirms the result in SPRS. No outside auditor is required at Level 1.

If you handle Controlled Unclassified Information (CUI), you are at Level 2, which usually involves a third-party assessment by a C3PAO. Level 1 is still the foundation that Level 2 builds on, so this tool remains useful groundwork, but it is not your Level 2 assessment.

A note on numbering: the 2026 FAR overhaul renumbered FAR 52.204-21 to FAR 52.240-93 for solicitations issued after February 1, 2026. The 15 requirements are unchanged, older contracts still cite 52.204-21, and the CMMC rule itself (32 CFR Part 170) still points to 52.204-21. The tool shows both numbers where it matters.

A note on naming: Executive Order 14347 (September 2025) authorized "Department of War" (DoW) as a secondary title for the Department of Defense. The statutory name is still Department of Defense, which is what the CMMC rule, the FAR and DFARS clauses, and SPRS use, so this tool and these docs use DoD. As of 2026, legislation to make Department of War the permanent legal name was pending.

## Who it is for

- **Business owners and IT leads** at companies that hold FCI and want to understand Level 1 before spending money on it.
- **Companies preparing for Level 2** who want to document the Level 1 foundation first.
- **Consultants and RPs** who want a vendor-neutral, plain-English reference to share with clients. See [Licensing and reuse](#licensing-and-reuse).

## How to use it

1. **Open the file.** Download `index.html` and open it in your browser. Nothing installs. You can work offline.
2. **Enter your details.** Used only to label your exports. They live in your saved file and are never sent anywhere.
3. **Set your scope.** Say whether you handle FCI or CUI, then map where your data lives. Shrinking that footprint is the single biggest cost saver, because every system FCI touches has to meet all 17 practices.
4. **Work the 59 objectives.** For each one, mark Met, Not met, or N/A, add a short note on how, and record your evidence. A practice counts as met only when every one of its objectives is met and evidence is on file.
5. **Watch the readiness bar.** Level 1 is pass or fail, so every applicable objective has to be Met before you can attest.
6. **Export when ready.** Generate a System Security Plan as Word or PDF, or a CSV for tracking. The export includes a gap report and an optional planning appendix.
7. **Save to resume, version, or hand off.** Save writes a small, date- and time-stamped file of your answers that you can reopen later or pass to a teammate or advisor. Each save is a version snapshot, and the built-in Compare feature shows exactly what changed between two of them.

## How to trust it

You do not have to take our word for any of this. You can verify it.

- **It is one file.** Everything is in `index.html`. No build step, no bundle, no hidden dependencies. Open it in a text editor and read it.
- **It runs offline.** Disconnect from the internet and it still works. There are no analytics, no trackers, and no external scripts. A Content Security Policy in the file blocks network connections outright (`connect-src 'none'`).
- **It collects nothing.** Your answers never leave your device. The only way data leaves is when you choose to save or export a file.
- **It is open source.** The full source is in this repository under an open license. Inspect it, fork it, or have someone review it.
- **Content fingerprint.** Every export and saved file carries a short fingerprint computed from your answers. The same answers always produce the same code. If a saved file is hand-edited, the tool flags the mismatch when you reload it. This is tamper-evidence and version identity, not a cryptographic signature, and it is labeled that way in the tool.

## What it does not do

Being honest about the boundaries protects you.

- It does **not** perform or replace a certified assessment, and using it does **not** affirm your CMMC status in SPRS.
- It does **not** warrant or guarantee CMMC approval.
- It is **not** legal or compliance advice. It is educational software.
- It cannot make judgment calls for you. Whether evidence is sufficient, or whether you truly hold FCI versus CUI, are questions for a qualified person. A CMMC professional can be hired by the hour, the way you would a lawyer.

Registered Practitioners (RPs) advise and prepare clients but do not perform certified assessments or affirm CMMC status. Independent Level 2 assessments are not possible without C3PAO affiliation. Keep that scope-of-practice boundary in mind for anything beyond Level 1.

## Authoritative sources

This tool points only to primary government sources. Verify anything here against them.

- [FAR 52.204-21](https://www.ecfr.gov/current/title-48/chapter-1/subchapter-H/part-52/subpart-52.2/section-52.204-21) (the 15 requirements; now also numbered 52.240-93)
- [NIST SP 800-171 Rev 2](https://csrc.nist.gov/pubs/sp/800/171/r2/upd1/final) (the CMMC baseline; its withdrawn banner is expected, see below)
- [NIST SP 800-171 Rev 3](https://csrc.nist.gov/pubs/sp/800/171/r3/final) (newer, not yet required for CMMC)
- [32 CFR Part 170](https://www.ecfr.gov/current/title-32/part-170) (the CMMC program rule, effective December 2024)
- DoD CMMC Level 1 [Assessment Guide](https://dodcio.defense.gov/Portals/0/Documents/CMMC/AssessmentGuideL1v2.pdf) and [Scoping Guide](https://dodcio.defense.gov/Portals/0/Documents/CMMC/ScopingGuideL1v2.pdf)
- [SPRS](https://www.sprs.csd.disa.mil/) (where you post your result and affirm)
- [NARA CUI Registry](https://www.archives.gov/cui/registry/category-list) (the authoritative list of what is CUI)

CMMC is still assessed against NIST SP 800-171 Revision 2. When you open the Rev 2 page at NIST you will see a banner saying it was withdrawn and superseded by Rev 3. That is NIST catalog housekeeping, not a CMMC change. The CMMC rule still points to Rev 2, so Rev 2 remains the correct baseline for your assessment.

## Licensing and reuse

This project uses two licenses so that both the software and the explanatory content can be reused cleanly.

- **Code** (the tool, its logic, and markup) is licensed under the **Apache License 2.0**. See [LICENSE](LICENSE).
- **Content** (the plain-English explanations, guidance text, and educational copy) is licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**. See [LICENSE-CONTENT](LICENSE-CONTENT).

What this means in practice:

- **SMBs** can use the tool for any purpose, including commercial work, at no cost.
- **Consultants and RPs** are welcome to share, adapt, and build on the content with their clients, including in paid engagements, as long as they give attribution. A reasonable attribution is: "Based on CMMC for SMBs by BluVi LLC, licensed CC BY 4.0, https://bluvi.ai." Attribution keeps the work honest and traceable to its sources; it does not imply endorsement.

If you adapt the content, please do not present it in a way that suggests BluVi LLC endorses your services, and please keep the authoritative-source links intact so clients can verify.

## Contributing

Corrections and improvements are welcome, especially fixes backed by a primary `.gov`, NIST, CFR, or NARA source. See [CONTRIBUTING.md](CONTRIBUTING.md). Content corrections must cite an authoritative source.

## Maintainer

Built and maintained by **BluVi LLC**, a fractional CISO practice focused on protecting small defense contractors from overpaying for compliance. Website: [bluvi.ai](https://bluvi.ai).

## Disclaimer

This tool is provided for educational purposes, as is, without warranty of any kind. It is not affiliated with or endorsed by the Department of Defense (also designated the Department of War under Executive Order 14347, September 2025), the Cyber AB, or ISACA. CMMC requirements and references change over time. Always confirm against the official sources before you attest.
