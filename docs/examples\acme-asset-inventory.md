# Asset and device inventory (example)

> Illustrative example for the fictional Acme Precision Machining, LLC, companion to `acme-machine-shop-ssp.md`. This is the artifact the SSP refers to as the device inventory, and it is the foundation for everything else: you cannot scope or secure what you have not listed. Adapt it to your shop. Not legal advice.

| | |
|---|---|
| Document owner | Dana Reyes, Owner |
| Effective date | 2026-06-05 |
| Next review | At every equipment or staffing change, and at least annually |
| Supports | Scoping, AC.L1-3.1.1[c], IA.L1-3.5.1[c], the in-scope footprint in the SSP |

**Purpose.** List everything that stores, processes, or transmits Federal Contract Information (FCI), and record what is deliberately out of scope and why. This is what the Level 1 Scoping Guide asks you to be able to show.

## Inventory

| Asset | Type | Where it is | Handles FCI? | In scope | Notes |
|---|---|---|---|---|---|
| 8 Windows 11 laptops and desktops | Endpoint | Office and front shop | Yes, staff access FCI | In scope | Enrolled in Microsoft 365, anti-malware on |
| Microsoft 365 tenant (Exchange, SharePoint, OneDrive) | Cloud service | Cloud | Yes, FCI is emailed and stored here | In scope | FCI lives in one restricted SharePoint library |
| Business firewall and router | Network | Office cabinet | Transmits | In scope | The external boundary; deny by default |
| Multifunction printer and scanner | Peripheral | Office | Possibly, scans of drawings | In scope | Has internal storage; cleared on disposal |
| Backup (Microsoft 365 backup and one external drive) | Backup | Cloud and locked cabinet | Yes, copies of FCI | In scope | Often missed; backups of FCI are in scope |
| 2 CNC machine controllers | Operational tech | Shop floor | No | Out of scope | Run G-code only; drawings and FCI never stored on them |
| Staff personal phones | Mobile | Various | No | Out of scope | Blocked from the FCI library; not used for FCI |
| Guest Wi-Fi | Network | Office | No | Out of scope | Separate network, cannot reach work systems |

## How scope was decided

In scope is anything that an authorized person uses to handle FCI, plus the things that protect it. For Acme that is the laptops, the Microsoft 365 services where FCI is emailed and stored, the firewall that guards the boundary, the printer that can hold a scanned drawing, and the backups that contain copies of FCI.

Out of scope is anything that does not store, process, or transmit FCI. The CNC controllers are the clearest example. A machinist loads G-code generated from a drawing, but the drawing and the FCI stay on the laptops and in Microsoft 365. The controller never holds FCI, so it is out of scope, and that reasoning is written here so it can be explained later. Personal phones are out because they are blocked from FCI. Guest Wi-Fi is out because it is separated from the work network.

The reasoning matters as much as the list. An assessor or a future reviewer will accept "out of scope" only if you can say why. Keeping the line clear is also what keeps Level 1 small and affordable, since every asset you pull into scope is something you then have to protect and document.

**Evidence it is in place.** This inventory, kept current and dated, reviewed whenever equipment or staff change. The Microsoft 365 device list backs up the endpoint entries.
