# How CMMC Level 1 actually works

A plain-language orientation for a small business, written to sit underneath the worked examples in this folder. Read this first. It explains whether you are even Level 1, what Level 1 requires, what you do with the result, and why it has to be true. None of this is legal advice.

## The example set, and how the pieces fit

- This primer: how the process works and what is required.
- `examples/acme-asset-inventory.md`: the foundation. What you have, and what is in or out of scope.
- `examples/acme-machine-shop-ssp.md`: the assessment record. How a fictional shop meets all 59 objectives, with two honest gaps.
- `examples/acme-evidence-pack.md`: the supporting documents the SSP points to, written out.

Everything uses one fictional company, Acme Precision Machining, so you can follow a single thread from "what do I own" to "here is my plan and the proof behind it."

## 1. Are you even Level 1?

This is the first question and the most expensive one to get wrong. Level depends on the kind of government information you handle.

Federal Contract Information (FCI) is information provided by or generated for the government under a contract that is not meant for public release. Quotes, drawings, purchase orders, statements of work. If your contract includes FAR 52.204-21 (renumbered 52.240-93 in solicitations issued after February 1, 2026) and nothing about CUI, you are almost certainly Level 1.

Controlled Unclassified Information (CUI) is a defined category the government marks and protects more tightly. The signal is usually the clause DFARS 252.204-7012 in your contract, a requirement to follow NIST SP 800-171, or material marked "CUI." If any of those apply, you are Level 2, the obligation is much larger, and this tool is not the right one for you.

How to check: read your contract clauses, look at the markings on what you receive, and if it is unclear, ask your prime or the contracting officer in writing. Do not guess. Treating CUI as if it were FCI leaves you under-protected and affirming something untrue. Treating FCI as if it were CUI can cost tens of thousands of dollars you did not need to spend, which is the exact trap a careful small business should avoid.

## 2. What Level 1 requires

Level 1 is the 15 safeguarding requirements of FAR 52.204-21, expressed by the DoD as 17 practices and 59 assessment objectives. They are basic security hygiene: who can get in, prove who they are, protect your boundary, run anti-malware, control physical access, and wipe media before you throw it out.

You assess yourself. At Level 1 there is no outside auditor and no C3PAO, and under 32 CFR Part 170 that self-assessment is permanent for Level 1. You then post your result and a senior official's affirmation in SPRS, the Supplier Performance Risk System. Since the acquisition rule took effect, that posting is a condition of award on covered contracts.

Level 1 is pass or fail, and there is no Plan of Action and Milestones. Every one of the 17 practices must be Met. This is the part people misread: in the example SSP, "56 of 59 objectives met" is not ninety-five percent of the way there. Two practices are not met, so the honest status is not ready, and you cannot truthfully affirm until they are closed. A count that looks almost done can still be a fail.

It repeats every year. You reassess and re-affirm in SPRS annually.

## 3. Why it has to be true

A senior official in your company signs the affirmation. That signature is a statement to the federal government. Affirming that you meet Level 1 when you do not is a false statement, and since 2021 the Department of Justice's Civil Cyber-Fraud Initiative has used the False Claims Act against contractors that misrepresented their cybersecurity compliance, with multi-million-dollar settlements. Whistleblowers, often current or former employees, can bring those cases and share in the recovery.

This is the real reason a confidently wrong SSP is worse than an honest, unfinished one. The documents are not bureaucracy for its own sake. They are what protects the person who signs. Defensible means it would hold up if someone looked, because someday someone might.

## 4. What you keep, and for how long

At Level 1 you do not submit your SSP to anyone. You keep it, and the evidence behind it, on file. You produce it if there is ever a dispute, a government review, or the day you grow into Level 2 and need the foundation already built.

Keep the proof current. A screenshot from two years ago showing multi-factor authentication turned on does not prove it is on today. Date your evidence, and refresh it when you do your annual reassessment. Retain records at least through the life of the contract and for a reasonable period after, in line with your contract's record-retention terms.

## 5. The floor versus good practice

Level 1 has a real floor, and knowing exactly where it sits is how you avoid being oversold. Some smart, nearly free security goes beyond what Level 1 requires. Multi-factor authentication is the clearest example: it is excellent, it is built into Microsoft 365, and the example shop uses it, but MFA is NIST 800-171 control 3.5.3, which is Level 2. Level 1 authentication, control 3.5.2, is met by a password. Likewise, strict least privilege is a Level 2 control, although limiting access to what a job needs maps naturally to the Level 1 practice on permitted functions.

Do the good practices because they protect your business, not because someone told you Level 1 demands them. If a vendor insists Level 1 requires a long list of tools and services, this is the line to check them against.

## 6. Anatomy of one met control

To make "policy plus proof" concrete, follow a single control all the way through. Take AC.L1-3.1.1, Authorized Access Control.

- The requirement: limit system access to authorized users, processes, and devices.
- The objectives: six of them, covering identifying your users and devices and limiting access to them.
- The policy that addresses it: the Access Control Policy in the evidence pack, which says everyone has an individual login, the owner approves new accounts, and access is removed the same day someone leaves.
- The proof it is real: the current Microsoft 365 user list, the device inventory, and the short list of who holds administrator rights.

That chain, requirement to objective to written policy to current proof, is what every Met practice should be able to show. A policy with no proof is a claim. Proof with no policy is an accident. An assessor, or your own affirmation, tests the pair.

## Authoritative sources

- FAR 52.204-21, the 15 requirements: https://www.ecfr.gov/current/title-48/chapter-1/subchapter-H/part-52/subpart-52.2/section-52.204-21
- 32 CFR Part 170, the CMMC Program rule: https://www.ecfr.gov/current/title-32/part-170
- CMMC Level 1 Scoping Guide: https://dodcio.defense.gov/Portals/0/Documents/CMMC/ScopingGuideL1v2.pdf
- CMMC Level 1 Assessment Guide: https://dodcio.defense.gov/Portals/0/Documents/CMMC/AssessmentGuideL1v2.pdf
- SPRS, where you post your result and affirmation: https://www.sprs.csd.disa.mil/
- NARA CUI Registry, to understand what CUI is: https://www.archives.gov/cui/registry/category-list
