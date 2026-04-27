# VU#653116 — Gardyn IoT Security Assessment

> CISA Advisory [ICSA-26-055-03](https://www.cisa.gov/news-events/ics-advisories/icsa-26-055-03) covers 10 published CVEs (initial advisory + Update A). Additional findings beyond the published advisory exist and are not enumerated in this repository.

| | |
|---|---|
| **Case** | CERT/CC VU#653116 |
| **CISA Advisory** | [ICSA-26-055-03](https://www.cisa.gov/news-events/ics-advisories/icsa-26-055-03) |
| **Researcher** | Michael Groberman — Gr0m |
| **Published** | 2026-02-24 |
| **Vendor** | Gardyn |
| **Products** | Gardyn Home Kit 1.0, 2.0, 3.0; Gardyn Studio 1.0, 2.0 |
| **Registered Devices** | 138,160+ |
| **User Accounts** | 134,215 |

---

## CVE Mapping

10 CVEs have been assigned. ICSA-26-055-03 (initial, 2026-02-24) covered 4 CVEs; Update A (2026-04-02) added 6 more for a total of 10.

| CVE | CVSS | CWE | Gr0m Finding | Title | Advisory | Detail Repo |
|-----|------|-----|-------------|-------|----------|-------------|
| [CVE-2026-28766](https://www.cve.org/CVERecord?id=CVE-2026-28766) | 9.3 | CWE-306 | Gr0m-006 | Missing Authentication on User Account Endpoint | Update A | [MichaelAdamGroberman/CVE-2026-28766](https://github.com/MichaelAdamGroberman/CVE-2026-28766) |
| [CVE-2025-1242](https://www.cve.org/CVERecord?id=CVE-2025-1242) | 9.1 | CWE-798 | Gr0m-003 | Hardcoded IoT Hub Administrative Credential | Initial | [MichaelAdamGroberman/CVE-2025-1242](https://github.com/MichaelAdamGroberman/CVE-2025-1242) |
| [CVE-2025-29631](https://www.cve.org/CVERecord?id=CVE-2025-29631) | 9.1 | CWE-78 | Gr0m-032 | OS Command Injection — Remote Code Execution | Initial | — |
| [CVE-2026-25197](https://www.cve.org/CVERecord?id=CVE-2026-25197) | 9.1 | CWE-639 | Gr0m-007, Gr0m-023 | Authorization Bypass via User-Controlled Key (IDOR) | Update A | [MichaelAdamGroberman/CVE-2026-25197](https://github.com/MichaelAdamGroberman/CVE-2026-25197) |
| [CVE-2025-10681](https://www.cve.org/CVERecord?id=CVE-2025-10681) | 8.6 | CWE-798 | Gr0m-004 | Hardcoded Cloud Storage Account Key | Update A | [MichaelAdamGroberman/CVE-2025-10681](https://github.com/MichaelAdamGroberman/CVE-2025-10681) |
| [CVE-2025-29628](https://www.cve.org/CVERecord?id=CVE-2025-29628) | 8.3 | CWE-319 | — | Cleartext Transmission of Sensitive Information | Initial | — |
| [CVE-2025-29629](https://www.cve.org/CVERecord?id=CVE-2025-29629) | 8.3 | CWE-1392 | — | Use of Default Credentials | Initial | — |
| [CVE-2026-32646](https://www.cve.org/CVERecord?id=CVE-2026-32646) | 7.5 | CWE-306 | Gr0m-008 | Missing Authentication on Admin Device Management | Update A | [MichaelAdamGroberman/CVE-2026-32646](https://github.com/MichaelAdamGroberman/CVE-2026-32646) |
| [CVE-2026-28767](https://www.cve.org/CVERecord?id=CVE-2026-28767) | 5.3 | CWE-306 | Gr0m-009 | Missing Authentication on Admin Notifications | Update A | [MichaelAdamGroberman/CVE-2026-28767](https://github.com/MichaelAdamGroberman/CVE-2026-28767) |
| [CVE-2026-32662](https://www.cve.org/CVERecord?id=CVE-2026-32662) | 5.3 | CWE-489 | Gr0m-019 | Active Debug Code in Production | Update A | [MichaelAdamGroberman/CVE-2026-32662](https://github.com/MichaelAdamGroberman/CVE-2026-32662) |

CVE-2025-29628, CVE-2025-29629, and CVE-2025-29631 were originally discovered by [mselbrede](https://github.com/mselbrede/gardyn) in February 2025 and independently confirmed by this research. A mirror is also available at [kristof-mattei/gardyn-hack](https://github.com/kristof-mattei/gardyn-hack).

---

## Published Findings

This repository surfaces only the findings that have been assigned CVE identifiers and published in the CISA advisory. Additional findings beyond the published advisory exist and are not enumerated here. Full technical details were provided to CISA and the vendor through CERT/CC VINCE (case VU#653116).

See the **CVE Mapping** table above for the complete list of published CVEs.

---

## Public Coordination Timeline

This timeline includes only (a) events published by CISA in ICSA-26-055-03, (b) the researcher's own disclosure actions, (c) observable changes in vendor API behavior or credentials, and (d) firmware compile/deployment dates derived from public version strings. Content from the CERT/CC VINCE coordination platform is embargoed and not included in this repository.

The researcher is a New Jersey resident and a Gardyn customer who purchased the affected device. Most security-disclosure events below are taken in **researcher capacity**; data-rights and regulatory filings are taken in **consumer capacity** under the New Jersey Data Privacy Act and related consumer-protection regimes. The vendor disclosure and CERT/CC / CISA disclosure activity is **dual-capacity** (researcher *and* consumer) because the researcher's own account record was visible in the unauthenticated `/api/users` response (CVE-2026-28766) — the report to CISA is the conduct of an affected Gardyn customer who also happens to be a researcher, not third-party-researcher conduct on behalf of unrelated data subjects. See [`TIMELINE.md`](TIMELINE.md) for the standing/capacity note.

| Date | Event | Type |
|------|-------|------|
| 2025-10-14 | Initial disclosure to vendor — included the mass PII exposure on `/api/users` (researcher's own account record visible in the unauthenticated response — direct standing as an affected data subject) and OS command-injection RCE on a Gardyn device the researcher owned | Researcher + consumer action (dual-capacity) |
| 2025-12-11 | Disclosure to CERT/CC / CISA (58 days after the initial vendor disclosure that already included the PII finding) | Researcher + consumer action (dual-capacity) / observable communication gap |
| 2025-12-18 | `/api/users` endpoint stopped returning data to unauthenticated requests | Observable vendor action |
| 2026-01-19 | Filed Personal Information Access Request (PIAR) with Gardyn Inc. as a Gardyn customer requesting disclosure of personal data held under the operative privacy policy then in effect | Consumer action |
| 2026-01-19 | Firmware master.583 deployed (build date encoded in version string `master.583.20260119`) | Firmware deployment |
| 2026-01-22 | `iothubowner` Azure IoT Hub administrative credential rotated (the previously distributed key stopped working) | Observable vendor action |
| 2026-01-27 | Gardyn customer support responded to the 2026-01-19 PIAR with written representations including: *"we do not maintain or generate user-facing logs that track individual access events"*; that personal information is not shared outside Gardyn; that telemetry is used solely for device functionality and diagnostics; that the customer's Wi-Fi password is not viewable by Gardyn staff; and that Gardyn does not have access to the customer's full credit card information. The "no user-facing access logs" representation is the source for the access-logging gap referenced in the CVE-2026-28766 evidence record. Several of these representations are independently in tension with the published privacy policy and/or with the CISA advisory's documented exposure of partial payment card data (`last_four`). Personal name of the responding agent redacted | Consumer action / vendor representation |
| 2026-02-24 | Vendor's public security page published at https://mygardyn.com/security/ | Vendor public statement |
| 2026-02-24 | **ICSA-26-055-03 published (initial — 4 CVEs)** | CISA |
| 2026-02-24 | Vendor announces firmware master.619 deployment | Vendor public statement |
| 2026-02-27 | SecurityWeek: ["Critical Flaws Exposed Gardyn Smart Gardens to Remote Hacking"](https://www.securityweek.com/critical-flaws-exposed-gardyn-smart-gardens-to-remote-hacking/) | Press coverage |
| 2026-04-02 | **ICSA-26-055-03 Update A published (10 CVEs total; CVE-2025-29631 remediated in firmware master.622)** | CISA |
| 2026-04-07 | Vendor's public security page at https://mygardyn.com/security/ updated | Vendor public statement |
| 2026-04-09 | Filed consumer data access request with Gardyn Inc.; Gardyn Privacy Team acknowledged receipt the same day and confirmed processing under the New Jersey Data Privacy Act based on residency | Consumer action / vendor acknowledgment |
| 2026-04-09 | SecurityWeek updated its 2026-02-27 article to reflect CISA Update A and the partial-payment-card detail: ["Critical Flaws Exposed Gardyn Smart Gardens to Remote Hacking"](https://www.securityweek.com/critical-flaws-exposed-gardyn-smart-gardens-to-remote-hacking/) | Press coverage |
| 2026-04-13 | Received correspondence from outside counsel at Clark Hill LLP representing Gardyn Inc. in connection with this matter | Observable communication |
| 2026-04-25 | Filed supplement to NJDPA right-to-know request with Gardyn Privacy Team referencing the April 9, 2026 acknowledgment and the approximate May 24, 2026 statutory response deadline | Consumer action |
| 2026-04-25 | Filed supplement to consumer complaint referred to NJ Division of Consumer Affairs from the New York Office of the Attorney General | Consumer action |
| 2026-04-25 | Reviewed publicly available state AG breach notification databases for CA, ME, MD, TX, VT, and NJ; no breach notification by Gardyn Inc. found in any reviewed database as of this date | Researcher action / verifiable absence |

### Advisory excerpt and researcher observations

- Per ICSA-26-055-03 Update A, the advisory describes CVE-2026-28766 (CVSS 9.3) as: "A specific endpoint exposes all user account information for registered Gardyn users without requiring authentication."
- Researcher observation (not advisory language): capture of the affected endpoint's JSON response showed approximately 134,215 user records, with fields including names, email addresses, phone numbers, and a `last_four` field for payment cards (populated for paying subscribers). Consistent with CISA's description above.
- Researcher observation — access logging gap (not advisory language): during coordinated disclosure correspondence the researcher reported to coordinating parties that the affected HTTP cloud backend lacked authentication-level access logging, and this assertion was not refuted by the vendor in subsequent coordinated correspondence. Separately, Gardyn customer support, in response to a researcher inquiry, stated that no access logs were available.

See [`TIMELINE.md`](TIMELINE.md) for the canonical narrative version of this timeline.

---

## References

- [ICSA-26-055-03 — CISA ICS Advisory](https://www.cisa.gov/news-events/ics-advisories/icsa-26-055-03)
- [CSAF JSON](https://raw.githubusercontent.com/cisagov/CSAF/develop/csaf_files/OT/white/2026/icsa-26-055-03.json)
- CERT/CC VU#653116 (vulnerability note, not publicly accessible)
- [Gardyn Security Page](https://mygardyn.com/security/)

---

**Researcher:** Michael Groberman — Gr0m
**Case:** CERT/CC VU#653116 / CISA ICSA-26-055-03
