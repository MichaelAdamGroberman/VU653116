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

| CVE | CVSS | CWE | Gr0m Finding | Title | Advisory |
|-----|------|-----|-------------|-------|----------|
| [CVE-2026-28766](https://www.cve.org/CVERecord?id=CVE-2026-28766) | 9.3 | CWE-306 | Gr0m-006 | Missing Authentication on User Account Endpoint | Update A |
| [CVE-2025-1242](https://www.cve.org/CVERecord?id=CVE-2025-1242) | 9.1 | CWE-798 | Gr0m-003 | Hardcoded IoT Hub Administrative Credential | Initial |
| [CVE-2025-29631](https://www.cve.org/CVERecord?id=CVE-2025-29631) | 9.1 | CWE-78 | Gr0m-032 | OS Command Injection — Remote Code Execution | Initial |
| [CVE-2026-25197](https://www.cve.org/CVERecord?id=CVE-2026-25197) | 9.1 | CWE-639 | Gr0m-007, Gr0m-023 | Authorization Bypass via User-Controlled Key (IDOR) | Update A |
| [CVE-2025-10681](https://www.cve.org/CVERecord?id=CVE-2025-10681) | 8.6 | CWE-798 | Gr0m-004 | Hardcoded Cloud Storage Account Key | Update A |
| [CVE-2025-29628](https://www.cve.org/CVERecord?id=CVE-2025-29628) | 8.3 | CWE-319 | — | Cleartext Transmission of Sensitive Information | Initial |
| [CVE-2025-29629](https://www.cve.org/CVERecord?id=CVE-2025-29629) | 8.3 | CWE-1392 | — | Use of Default Credentials | Initial |
| [CVE-2026-32646](https://www.cve.org/CVERecord?id=CVE-2026-32646) | 7.5 | CWE-306 | Gr0m-008 | Missing Authentication on Admin Device Management | Update A |
| [CVE-2026-28767](https://www.cve.org/CVERecord?id=CVE-2026-28767) | 5.3 | CWE-306 | Gr0m-009 | Missing Authentication on Admin Notifications | Update A |
| [CVE-2026-32662](https://www.cve.org/CVERecord?id=CVE-2026-32662) | 5.3 | CWE-489 | Gr0m-019 | Active Debug Code in Production | Update A |

CVE-2025-29628, CVE-2025-29629, and CVE-2025-29631 were originally discovered by [mselbrede](https://github.com/mselbrede/gardyn) in February 2025 and independently confirmed by this research. A mirror is also available at [kristof-mattei/gardyn-hack](https://github.com/kristof-mattei/gardyn-hack).

---

## Published Findings

This repository surfaces only the findings that have been assigned CVE identifiers and published in the CISA advisory. Additional findings beyond the published advisory exist and are not enumerated here. Full technical details were provided to CISA and the vendor through CERT/CC VINCE (case VU#653116).

See the **CVE Mapping** table above for the complete list of published CVEs.

---

## Public Coordination Timeline

This timeline includes only (a) events published by CISA in ICSA-26-055-03, (b) the researcher's own disclosure actions, (c) observable changes in vendor API behavior or credentials, and (d) firmware compile/deployment dates derived from public version strings. Content from the CERT/CC VINCE coordination platform is embargoed and not included in this repository.

The researcher is a New Jersey resident and a Gardyn customer who purchased the affected device. Security-disclosure events below are taken in **researcher capacity**; data-rights and regulatory filings are taken in **consumer capacity** under the New Jersey Data Privacy Act and related consumer-protection regimes. See [`TIMELINE.md`](TIMELINE.md) for the standing/capacity note.

| Date | Event | Type |
|------|-------|------|
| 2025-10-14 | Initial disclosure to vendor (researcher action) | Researcher action |
| 2025-12-11 | Disclosure to CERT/CC (58 days after the initial vendor disclosure) | Researcher action / observable communication gap |
| 2025-12-18 | `/api/users` endpoint stopped returning data to unauthenticated requests | Observable vendor action |
| 2026-01-19 | Firmware master.583 deployed (build date encoded in version string `master.583.20260119`) | Firmware deployment |
| 2026-01-22 | `iothubowner` Azure IoT Hub administrative credential rotated (the previously distributed key stopped working) | Observable vendor action |
| 2026-02-24 | Vendor's public security page published at https://mygardyn.com/security/ | Vendor public statement |
| 2026-02-24 | **ICSA-26-055-03 published (initial — 4 CVEs)** | CISA |
| 2026-02-24 | Vendor announces firmware master.619 deployment | Vendor public statement |
| 2026-04-02 | **ICSA-26-055-03 Update A published (10 CVEs total; CVE-2025-29631 remediated in firmware master.622)** | CISA |
| 2026-04-07 | Vendor's public security page at https://mygardyn.com/security/ updated (timing relative to Update A is publicly observable via the Wayback Machine) | Vendor public statement |
| 2026-04-09 | Filed consumer data access request with Gardyn Inc.; Gardyn Privacy Team acknowledged receipt the same day and confirmed processing under the New Jersey Data Privacy Act based on residency | Consumer action / vendor acknowledgment |
| 2026-04-13 | Received correspondence from outside counsel at Clark Hill LLP representing Gardyn Inc. in connection with this matter | Observable communication |
| 2026-04-25 | Filed supplement to NJDPA right-to-know request with Gardyn Privacy Team referencing the April 9, 2026 acknowledgment and the approximate May 24, 2026 statutory response deadline | Consumer action |
| 2026-04-25 | Filed supplement to consumer complaint referred to NJ Division of Consumer Affairs from the New York Office of the Attorney General | Consumer action |
| 2026-04-25 | Reviewed publicly available state AG breach notification databases for CA, ME, MD, TX, VT, and NJ; no breach notification by Gardyn Inc. found in any reviewed database as of this date | Researcher action / verifiable absence |

### Federal record observations (per ICSA-26-055-03 Update A)

- CISA's published advisory states that the vendor reported to CISA that no access logging existed on the affected endpoints during the exposure window.
- CVE-2026-28766 (CVSS 9.3) documents an unauthenticated endpoint that returned approximately 134,215 user records including names, email addresses, phone numbers, and last four digits of payment cards.

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
