# Evidence pack (example)

### Worked supporting documents for the example Acme Machine Shop SSP

> Illustrative worked examples for the fictional Acme Precision Machining, LLC. These are the kind of short supporting documents the example System Security Plan (`acme-machine-shop-ssp.md`) points to. They show what defensible evidence looks like at Level 1. Adapt them to your own shop; copying them word for word does not make you compliant. A written policy is only half of it. You also have to be doing what it says and be able to show the proof, which is why each one ends with the records that demonstrate it is real. This is not legal advice.

Level 1 evidence is documentation-first: a short written policy or process, plus the artifacts that prove it is in place. None of these needs to be long. Yours should sound like your shop, not like a template.

### Two kinds of evidence

Evidence comes in two forms, and you usually need both. The written kind is the policies and procedures shown here, what you say you do. The proof kind is the screenshots, exported settings, lists, and logs that show you are actually doing it: a screenshot of multi-factor authentication enforced, the firewall rule export, the current user list, the disposal log. A binder of policies with no proof does not pass, and proof with no policy looks like an accident. The pair is what gets tested, so each document below ends with the proof that backs it.

### The Level 1 floor versus good practice

Some of these examples include security that is smart but goes beyond the Level 1 minimum, and you should know which is which so no one oversells you. Multi-factor authentication appears in the Authentication Standard because it is nearly free in Microsoft 365 and worth doing, but MFA is control 3.5.3, a Level 2 control, not a Level 1 requirement. Level 1 authentication is met by a password. Keep the good practices because they protect you, not because Level 1 demands them. See `../how-level-1-works.md` for more on where the floor sits.

---

## 1. Access Control Policy

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | 2027-06-05, or sooner on a major change |
| Supports | AC.L1-3.1.1, AC.L1-3.1.2, AC.L1-3.1.20 |

**Purpose.** Control who and what can reach the systems that hold Federal Contract Information (FCI).

**Scope.** Acme's Microsoft 365 tenant, company-managed devices, and the restricted SharePoint library where FCI is stored.

**Policy.**

1. Individual accounts. Every person has their own login. There are no shared or generic accounts.
2. Least privilege. The owner and the office manager hold administrator rights. Everyone else is a standard user. People are given access only to what their job needs.
3. Granting access. The owner approves any new account. Access to the FCI library is granted only to staff whose work requires it.
4. Devices. FCI is reached only from company-managed devices enrolled in Microsoft 365. Personal devices are blocked from the FCI library.
5. External systems. Only approved outside services (Microsoft 365, the prime's portal, the accounting software) are used for work. A new cloud app must be approved by the owner before anyone uses it for FCI.
6. Removing access. When someone leaves or changes roles, their access is removed or adjusted the same day and any keys are collected.
7. Review. This policy, the user list, and who holds administrator rights are reviewed at every staffing change and at least once a year.

**Evidence it is in place.** The current Microsoft 365 user list, the device inventory spreadsheet, and the short list of who holds administrator rights.

---

## 2. Authentication Standard

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | 2027-06-05, or sooner on a major change |
| Supports | IA.L1-3.5.1, IA.L1-3.5.2 |

**Purpose.** Confirm who someone is before they are allowed in.

**Scope.** All Microsoft 365 sign-ins and all company devices.

**Standard.**

1. Unique credentials. Each person signs in with their own account. Credentials are never shared.
2. Passwords. At least 12 characters, and staff are encouraged to use a passphrase. Common and previously breached passwords are blocked. Passwords are not forced to expire on a schedule; they are changed if there is any sign they were exposed. This follows current NIST guidance.
3. Multi-factor authentication. MFA is required on every Microsoft 365 sign-in, with no exceptions.
4. Default passwords. Any default or vendor password is changed before a device or service is put to use.
5. Device check. Only enrolled, compliant company devices may connect, enforced by Conditional Access.
6. Lockout. Accounts lock after repeated failed sign-in attempts.

> Level 1 note: the requirement here, control 3.5.2, is met by a unique password. The MFA in item 3 is control 3.5.3, a Level 2 measure Acme adopted because it is built into Microsoft 365 and is the single biggest reducer of account takeover. Useful, but not something Level 1 forces you to buy.

**Evidence it is in place.** A screenshot showing MFA enforced for all users, and the password and Conditional Access settings.

---

## 3. Flaw Remediation (Patch and Update) Process

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | 2027-06-05, or sooner on a major change |
| Supports | SI.L1-3.14.1 |

**Purpose.** Find and fix security flaws in a timely way. CMMC Level 1 does not set a deadline, so Acme sets its own and follows it. That is what the objectives ask for.

**Scope.** All company computers and phones, and the Microsoft 365 apps.

**Process.**

1. Automatic updates are turned on for every device and app.
2. The office manager reviews update and patch status once a week.
3. Timeframes, set by Acme:
   - Critical updates are reviewed weekly and applied within 7 days.
   - Anyone who notices a suspected problem reports it to the owner the same day.
4. If an update cannot be applied on time, the owner decides on a temporary protection and a target date to finish.

**Evidence it is in place.** A screenshot showing automatic updates enabled, and the dated note from the weekly review.

---

## 4. Media Sanitization Procedure

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | 2027-06-05, or sooner on a major change |
| Supports | MP.L1-3.8.3 |

> This is the procedure that closes the Section 3 gap in the example SSP. Writing it down and starting the disposal log is what moves MP.L1-3.8.3 from Not met to Met.

**Purpose.** Make sure FCI cannot be recovered from any media before it is thrown away or reused. Follows NIST SP 800-88.

**Scope.** Any media that has held FCI: computer drives, USB drives, phones, and paper.

**Procedure.**

1. Hard drives: a single full overwrite is generally enough, or physically destroy the drive.
2. Solid state drives: use the maker's secure erase, or encrypt the drive and then destroy the key.
3. Phones: factory reset with encryption on, or destroy.
4. Anything being discarded rather than reused: physically destroy it.
5. Paper that held FCI: cross-cut shred it.
6. Log every wipe or disposal: what the item was, the date, who did it, the method used, and keep any certificate of destruction.

**Responsibility.** The office manager performs or arranges sanitization. The owner approves disposal.

**Evidence it is in place.** The disposal log and any certificates of destruction. Reference: NIST SP 800-88 Rev 1, https://csrc.nist.gov/pubs/sp/800/88/r1/final

---

## 5. Visitor Log and Retention Note

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | 2027-06-05, or sooner on a major change |
| Supports | PE.L1-3.10.3, PE.L1-3.10.4 |

> This closes the second Section 3 gap in the example SSP. Acme already signs visitors in and escorts them; the missing piece was keeping the log. Writing down a retention rule and keeping the sheets moves PE.L1-3.10.4 from Not met to Met.

**Purpose.** Keep a record of who entered the premises and when.

**The log.** Each visitor is recorded with: date, name, company, purpose, time in, time out, and the staff member who escorted them.

**Retention.** CMMC sets no retention period, so Acme set one: logs are kept for one year. Paper sheets are scanned to the office computer monthly as a backup and stored in a dated folder.

**Responsibility.** Whoever greets the visitor records the entry. The office manager files the sheet and runs the monthly scan.

**Evidence it is in place.** The retained visitor logs, paper and scanned, for the current and prior period.

---

## 6. Physical Access Device (Key) List

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | At each staffing change, and at least annually |
| Supports | PE.L1-3.10.1, PE.L1-3.10.5 |

**Purpose.** Track keys and badges so physical access stays controlled.

**The list.** Each key or badge is recorded with: an identifier, the door or area it opens, who it is issued to, the date issued, and the date returned.

**Rules.**

1. Only the owner issues keys and badges.
2. Keys are collected when someone leaves or changes roles.
3. Spare keys are kept in a locked cabinet.
4. If a key is lost, the affected lock is rekeyed and the list updated.

**Evidence it is in place.** The current key list and a dated note of the last review.

---

## 7. Network Boundary Description

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | 2027-06-05, or sooner on a network change |
| Supports | SC.L1-3.13.1, SC.L1-3.13.5 |

**Purpose.** Describe where Acme's network meets the outside world and how that boundary is protected. A short description or a simple diagram both work.

**The boundary.**

1. The shop network meets the internet at the business firewall, which denies inbound connections by default and logs traffic.
2. A separate guest Wi-Fi network is provided for visitors. It cannot reach the work systems.
3. There are no public-facing servers on the work network. The company website is hosted by an outside provider.
4. Staff reach FCI through Microsoft 365 over encrypted connections. Nothing internal is exposed to the internet.

**Evidence it is in place.** This description, the firewall rule export showing deny by default, and the guest network settings.

---

## 8. Public-Posting Rule

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | Quarterly |
| Supports | AC.L1-3.1.22 |

**Purpose.** Make sure FCI never ends up on a public system such as the website or social media.

**The rule.**

1. The owner approves all public content before it is published.
2. FCI, customer drawings, and contract details are never posted publicly.
3. Public pages and social accounts are reviewed every quarter to confirm nothing slipped through.
4. Anything posted improperly is removed by the owner immediately.

**Evidence it is in place.** This one-page rule with the approver named, and a dated note of the last quarterly review.

---

*Examples for the fictional Acme Precision Machining, LLC, companion to `acme-machine-shop-ssp.md`. Provided for learning. Not a certification and not affiliated with or endorsed by the DoD, the Cyber AB, or ISACA.*
