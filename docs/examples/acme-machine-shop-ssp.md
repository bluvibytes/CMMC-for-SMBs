> **Illustrative example, faithful to the tool's export.** Acme Precision Machining, LLC is fictional, and so are every name, date, and detail below. This file reproduces the structure the tool actually generates, filled in for a diligently completed Level 1 self-assessment, so you can see what the System Security Plan hands you. Two things here go beyond a default export and are called out on purpose: the per-objective "Why / how" notes are filled in (the tool leaves those optional, with most detail living in the practice-level Evidence box), and this banner is added for the docs. The tool also supports marking an objective N/A with a justification when it genuinely does not apply; Acme has none. Learn from this, do not copy it verbatim. It is not a certification and not legal advice.

---

# Acme Precision Machining, LLC

## System Security Plan
### CMMC Level 1 (FAR 52.204-21) Self-Assessment Documentation

| | |
|---|---|
| Organization | Acme Precision Machining, LLC |
| System or enclave | Microsoft 365 business tenant and managed Windows endpoints |
| Prepared by | Dana Reyes, Owner |
| Assessment date | 2026-06-05 |
| Affirming senior official | Dana Reyes, Owner |
| Date generated | 2026-06-09 |
| Basis | FAR 52.204-21 (now 52.240-93), NIST SP 800-171A, DoD CMMC Level 1 Assessment Guide |

This is self-assessment documentation, not a certification, and is not affiliated with or endorsed by the DoD, the Cyber AB, or ISACA. This document records how the organization meets the 15 basic safeguarding requirements of FAR 52.204-21 (CMMC Level 1), expressed as 59 assessment objectives. A formal System Security Plan is NIST SP 800-171 control 3.12.4, which is a Level 2 requirement; presenting Level 1 in this form gives the foundation that carries into Level 2.

Prepared for SMBs, an open CMMC tool by BluVi LLC. bluvi.ai

Content fingerprint EXAMPLE-7F3A9C21, generated 2026-06-09. The same answers always produce this code; if it differs from a copy you were given, the contents were changed.

---

## 1. System Identification and Scope

| | |
|---|---|
| Level determination | Level 1 (FCI only) |
| Scope statement | FCI (technical drawings and purchase orders marked FCI) arrives by email from the prime and is stored in one restricted SharePoint library, accessed only from company-managed Windows devices. The CNC machine controllers are out of scope: they run G-code only and do not store or process FCI. |
| Assessment result | 56 of 59 objectives marked Met |
| Readiness | Not ready. 2 practices not met. Level 1 is pass or fail with no POA&M, so every not-met objective must be closed before attestation. |

### In-scope data footprint

| Where the data lives | Maps to practices |
|---|---|
| Email / mailboxes | AC, IA, SC |
| File shares, SharePoint, network drives | AC, IA |
| Cloud storage (OneDrive, Drive, Dropbox) | AC, SC |
| Backups (commonly missed) | AC, MP, SC |
| Company laptops, desktops, phones | AC, IA, SI |
| Paper / printouts | PE, MP |
| Printers / copiers with storage | MP, PE |
| Cloud apps / SaaS where FCI is entered | AC, IA, SC |

---

## 2. Control Implementation

17 practices, 59 assessment objectives. A practice is Met only when every objective is Met or justified N/A and evidence is recorded.

- FAR 52.204-21 (now 52.240-93), the 15 safeguarding requirements: https://www.ecfr.gov/current/title-48/chapter-1/subchapter-H/part-52/subpart-52.2/section-52.204-21
- NIST SP 800-171 Rev 2, the controls Level 1 maps to: https://csrc.nist.gov/pubs/sp/800/171/r2/upd1/final. CMMC uses Revision 2; NIST's page shows it withdrawn in favor of Revision 3, which CMMC has not yet adopted.
- CMMC Level 1 Assessment Guide, the 59 objectives: https://dodcio.defense.gov/Portals/0/Documents/CMMC/AssessmentGuideL1v2.pdf
- CMMC Level 1 Scoping Guide, what is in scope: https://dodcio.defense.gov/Portals/0/Documents/CMMC/ScopingGuideL1v2.pdf

### AC: Access Control

#### AC.L1-3.1.1 Authorized Access Control (MET)

**Requirement.** Limit information system access to authorized users, processes acting on behalf of authorized users, or devices (including other information systems).

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Authorized users are identified | MET | Microsoft 365 user list kept current by the office manager. |
| b | Processes acting on behalf of authorized users are identified | MET | No service accounts or automated jobs are in use; reviewed when systems change. |
| c | Devices (and other systems) authorized to connect to the system are identified | MET | Device inventory of the 8 company endpoints maintained in a spreadsheet. |
| d | System access is limited to authorized users | MET | Entra ID enforces named-account sign-in; no shared logins. |
| e | System access is limited to processes acting on behalf of authorized users | MET | None in use, so none can run. |
| f | System access is limited to authorized devices (including other systems) | MET | Only enrolled company devices can reach the FCI library; personal devices are blocked. |

**Evidence.** One-page access policy stating everyone gets an individual login and listing who may access what and how access is granted and removed; current Microsoft 365 user list; device inventory spreadsheet, reviewed at each staffing change.

Source: NIST SP 800-171 Rev 2, requirement 3.1.1 · FAR 52.204-21

#### AC.L1-3.1.2 Transaction & Function Control (MET)

**Requirement.** Limit information system access to the types of transactions and functions that authorized users are permitted to execute.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | The types of transactions and functions that authorized users are permitted to execute are defined | MET | Roles written down: owner and office manager are admins, machinists are standard users. |
| b | System access is limited to the defined types of transactions and functions for authorized users | MET | Microsoft 365 group permissions match those roles; admin rights held by two people only. |

**Evidence.** Short role-and-permissions note describing least privilege, a screenshot of the Microsoft 365 permission groups, and the list of who holds administrator rights.

Source: NIST SP 800-171 Rev 2, requirement 3.1.2 · FAR 52.204-21

#### AC.L1-3.1.20 External Connections (MET)

**Requirement.** Verify and control/limit connections to and use of external information systems.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Connections to external systems are identified | MET | Approved external services listed: Microsoft 365, the prime's portal, accounting software. |
| b | The use of external systems is identified | MET | Staff use only those approved services for work. |
| c | Connections to external systems are verified | MET | Access to the prime's portal uses named accounts confirmed by the prime. |
| d | The use of external systems is verified | MET | New cloud apps must be approved by the owner before use. |
| e | Connections to external systems are controlled/limited | MET | Firewall allow-list; the FCI library is reachable only from managed devices. |
| f | The use of external systems is controlled/limited | MET | FCI is handled on company devices and approved cloud apps only, not personal laptops. |

**Evidence.** Written list of approved outside systems and cloud services with the rules for connecting (company-managed devices only), plus the Conditional Access and firewall settings as proof.

Source: NIST SP 800-171 Rev 2, requirement 3.1.20 · FAR 52.204-21

#### AC.L1-3.1.22 Control Public Information (MET)

**Requirement.** Control information posted or processed on publicly accessible information systems.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Individuals authorized to post or process information on publicly accessible systems are identified | MET | The owner approves all website and social content. |
| b | Procedures to ensure FCI is not posted or processed on publicly accessible systems are identified | MET | Written rule: FCI never goes on public systems. |
| c | A review process is in place prior to posting of any content to publicly accessible systems | MET | Owner reviews any content before it is published. |
| d | Content on publicly accessible systems is reviewed to ensure that it does not include FCI | MET | Website and social accounts checked quarterly. |
| e | Mechanisms are in place to remove and address improper posting of FCI | MET | Owner has access to take down content immediately. |

**Evidence.** One-paragraph public-posting rule naming the approver and the review step, with a dated note of the last review.

Source: NIST SP 800-171 Rev 2, requirement 3.1.22 · FAR 52.204-21

### IA: Identification & Authentication

#### IA.L1-3.5.1 Identification (MET)

**Requirement.** Identify information system users, processes acting on behalf of users, or devices.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | System users are identified | MET | Every employee has a unique Entra ID account; no generic logins. |
| b | Processes acting on behalf of users are identified | MET | None in use. |
| c | Devices accessing the system are identified | MET | Devices enrolled and named in Microsoft 365. |

**Evidence.** User list showing every person has a unique account with no shared logins, referenced in the access policy.

Source: NIST SP 800-171 Rev 2, requirement 3.5.1 · FAR 52.204-21

#### IA.L1-3.5.2 Authentication (MET)

**Requirement.** Authenticate (or verify) the identities of those users, processes, or devices, as a prerequisite to allowing access to organizational information systems.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | The identity of each user is authenticated or verified as a prerequisite to system access | MET | Password plus MFA required for all Microsoft 365 sign-ins. |
| b | The identity of each process acting on behalf of a user is authenticated or verified as a prerequisite to system access | MET | None in use. |
| c | The identity of each device accessing or connecting to the system is authenticated or verified as a prerequisite to system access | MET | Device compliance required by Conditional Access before connecting. |

**Evidence.** Written authentication standard (password rules and where MFA is required), plus a screenshot showing MFA enforced and default passwords changed.

Source: NIST SP 800-171 Rev 2, requirement 3.5.2 · FAR 52.204-21

### MP: Media Protection

#### MP.L1-3.8.3 Media Disposal (NOT MET)

**Requirement.** Sanitize or destroy information system media containing Federal Contract Information before disposal or release for reuse.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | System media containing FCI is sanitized or destroyed before disposal | NOT MET | Old drives have been set aside, but no written procedure exists and no sanitization has been performed yet. |
| b | System media containing FCI is sanitized before it is released for reuse | NOT MET | No process in place for wiping a device before it is reassigned. |

**Evidence.** (none recorded)

Source: NIST SP 800-171 Rev 2, requirement 3.8.3 · FAR 52.204-21

### PE: Physical Protection

#### PE.L1-3.10.1 Limit Physical Access (MET)

**Requirement.** Limit physical access to organizational information systems, equipment, and the respective operating environments to authorized individuals.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Authorized individuals allowed physical access are identified | MET | Written list of who may enter the office and the network cabinet. |
| b | Physical access to organizational systems is limited to authorized individuals | MET | Office locked; only staff hold keys. |
| c | Physical access to equipment is limited to authorized individuals | MET | Network gear in a locked cabinet. |
| d | Physical access to operating environments is limited to authorized individuals | MET | Shop floor and office are not open to the public. |

**Evidence.** Note of which areas hold systems and network gear and who may enter, with a description of the locks and the network cabinet.

Source: NIST SP 800-171 Rev 2, requirement 3.10.1 · FAR 52.204-21

#### PE.L1-3.10.3 Escort Visitors (MET)

**Requirement.** Escort visitors and monitor visitor activity.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Visitors are escorted | MET | Guests are walked through by a staff member, not left alone. |
| b | Visitor activity is monitored | MET | Staff accompany visitors; an entrance camera covers the door. |

**Evidence.** Short written visitor rule (guests sign in and are escorted).

Source: NIST SP 800-171 Rev 2, requirement 3.10.3 · FAR 52.204-21

#### PE.L1-3.10.4 Physical Access Logs (NOT MET)

**Requirement.** Maintain audit logs of physical access.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Audit logs of physical access are maintained | NOT MET | Visitors sign in on a sheet at the door, but the sheets are not kept, so there is no retained log. |

**Evidence.** (none recorded)

Source: NIST SP 800-171 Rev 2, requirement 3.10.4 · FAR 52.204-21

#### PE.L1-3.10.5 Manage Physical Access Devices (MET)

**Requirement.** Control and manage physical access devices.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Physical access devices are identified | MET | Spreadsheet lists every key issued. |
| b | Physical access devices are controlled | MET | Keys held only by the owner, office manager, and lead machinists. |
| c | Physical access devices are managed | MET | Keys are collected when someone leaves or changes roles. |

**Evidence.** Key-issuance list showing who holds each key, with a note on collecting them at offboarding.

Source: NIST SP 800-171 Rev 2, requirement 3.10.5 · FAR 52.204-21

### SC: System & Communications Protection

#### SC.L1-3.13.1 Boundary Protection (MET)

**Requirement.** Monitor, control, and protect organizational communications at the external boundaries and key internal boundaries of the information systems.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | The external system boundary is defined | MET | Documented: the shop network meets the internet at the business firewall. |
| b | Key internal system boundaries are defined | MET | Work network and guest Wi-Fi are separate. |
| c | Communications are monitored at the external system boundary | MET | Firewall logging enabled. |
| d | Communications are monitored at key internal boundaries | MET | Guest network isolated and logged. |
| e | Communications are controlled at the external system boundary | MET | Firewall set to deny by default. |
| f | Communications are controlled at key internal boundaries | MET | Guest network cannot reach work systems. |
| g | Communications are protected at the external system boundary | MET | Remote work goes through Microsoft 365 over TLS; no internal systems exposed. |
| h | Communications are protected at key internal boundaries | MET | FCI library access is encrypted in transit. |

**Evidence.** Short written description of the network boundary plus the firewall rule list, exported, showing it blocks by default.

Source: NIST SP 800-171 Rev 2, requirement 3.13.1 · FAR 52.204-21

#### SC.L1-3.13.5 Public-Access System Separation (MET)

**Requirement.** Implement subnetworks for publicly accessible system components that are physically or logically separated from internal networks.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Publicly accessible system components are identified | MET | The only public-facing system is the company website. |
| b | Subnetworks for publicly accessible system components are physically or logically separated from internal networks | MET | The website is hosted by an outside provider; guest Wi-Fi is on its own network. |

**Evidence.** Simple network description showing the website is externally hosted and guest Wi-Fi is separated from work systems.

Source: NIST SP 800-171 Rev 2, requirement 3.13.5 · FAR 52.204-21

### SI: System & Information Integrity

#### SI.L1-3.14.1 Flaw Remediation (MET)

**Requirement.** Identify, report, and correct information and information system flaws in a timely manner.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | The time within which to identify system flaws is specified | MET | Patch policy: critical updates reviewed weekly. |
| b | System flaws are identified within the specified time frame | MET | Automatic update reporting reviewed each week. |
| c | The time within which to report system flaws is specified | MET | Policy: staff report problems to the owner the same day. |
| d | System flaws are reported within the specified time frame | MET | Followed in practice. |
| e | The time within which to correct system flaws is specified | MET | Policy: critical fixes applied within 7 days. |
| f | System flaws are corrected within the specified time frame | MET | Auto-updates plus the weekly check confirm patches applied. |

**Evidence.** Written patch and update process stating Acme's own timeframes (CMMC sets none), plus a screenshot showing automatic updates enabled.

Source: NIST SP 800-171 Rev 2, requirement 3.14.1 · FAR 52.204-21

#### SI.L1-3.14.2 Malicious Code Protection (MET)

**Requirement.** Provide protection from malicious code at appropriate locations within organizational information systems.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Designated locations for malicious code protection are identified | MET | Decided: all endpoints and email. |
| b | Protection from malicious code at designated locations is provided | MET | Microsoft Defender runs on every device; Exchange Online filters email. |

**Evidence.** Note of where anti-malware runs (all computers and email) and which product is used, with a screenshot of it active.

Source: NIST SP 800-171 Rev 2, requirement 3.14.2 · FAR 52.204-21

#### SI.L1-3.14.4 Update Malicious Code Protection (MET)

**Requirement.** Update malicious code protection mechanisms when new releases are available.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | Malicious code protection mechanisms are updated when new releases are available | MET | Defender updates its definitions and engine automatically. |

**Evidence.** Screenshot showing anti-malware definitions update automatically, noted in the process document.

Source: NIST SP 800-171 Rev 2, requirement 3.14.4 · FAR 52.204-21

#### SI.L1-3.14.5 System & File Scanning (MET)

**Requirement.** Perform periodic scans of the information system and real-time scans of files from external sources as files are downloaded, opened, or executed.

| Obj | Assessment objective | Status | Why / how |
|---|---|---|---|
| a | The frequency for malicious code scans is defined | MET | Policy: full scan weekly. |
| b | Malicious code scans are performed with the defined frequency | MET | Weekly full scan scheduled in Defender. |
| c | Real-time malicious code scans of files from external sources as files are downloaded, opened, or executed are performed | MET | Real-time protection on for downloads, USB, and email attachments. |

**Evidence.** Note of the scan settings (real-time on, weekly full scan), plus a screenshot of those settings.

Source: NIST SP 800-171 Rev 2, requirement 3.14.5 · FAR 52.204-21

---

## 3. Gaps to Close Before Attestation

| Practice | Finding | Action to close |
|---|---|---|
| MP.L1-3.8.3 Media Disposal | NOT MET | Resolve objectives not met: a, b. Record supporting evidence. Follow NIST SP 800-88 for sanitizing media: for hard drives a single full overwrite is generally enough, for solid state drives use the maker's secure erase or encrypt the drive and destroy the key, and physically destroy anything you discard. Shred paper. Write the procedure down and log each disposal. NIST SP 800-88 (Media Sanitization) |
| PE.L1-3.10.4 Physical Access Logs | NOT MET | Resolve objectives not met: a. Record supporting evidence. Keep a visitor log on paper or electronically. Decide and write down how long you retain it, store it somewhere safe, and scan paper sheets so you have a backup copy. |

---

## 4. Affirmation

I affirm that the information in this plan is accurate and that the organization meets the CMMC Level 1 requirements recorded as Met, to the best of my knowledge. Level 1 is reassessed and re-affirmed in SPRS annually.

Affirming senior official: Dana Reyes, Owner

Signature: ____________________________________     Date: __________________
