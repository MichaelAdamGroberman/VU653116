# Timeline

This timeline tracks publicly-known events related to CISA Advisory ICSA-26-055-03 / CERT/CC VU#653116. It includes only events visible in public records and the researcher's own actions. Coordination details from the CERT/CC VINCE platform are embargoed and not included.

## Capacity / Standing

The researcher is a New Jersey resident and a Gardyn customer who purchased the affected device. Events on this timeline are taken in two distinct capacities:

- **Researcher capacity** — security disclosure activity (vendor notification, CERT/CC coordination, CISA advisory publication). Standing arises from lawful research on a device owned by the researcher.
- **Consumer capacity** — data-rights and regulatory filings (NJDPA right-to-know request, NJ Division of Consumer Affairs complaint). Standing arises from being a Gardyn customer and a New Jersey resident, which is the basis Gardyn's Privacy Team cited when acknowledging the April 9, 2026 request under the New Jersey Data Privacy Act.

These tracks proceed in parallel and on separate legal bases.

## 2025

### 2025-10-14
Initial disclosure to Gardyn Inc. via support@mygardyn.com.

## 2026

### 2026-02-24
CISA published Advisory ICSA-26-055-03 covering four CVEs.

### 2026-02-27
SecurityWeek published reporting on CISA Advisory ICSA-26-055-03: ["Critical Flaws Exposed Gardyn Smart Gardens to Remote Hacking"](https://www.securityweek.com/critical-flaws-exposed-gardyn-smart-gardens-to-remote-hacking/).

### 2026-04-02 / 2026-04-04
CISA published Update A expanding the advisory to ten total CVEs.

### 2026-04-07
Vendor's public security page at <https://mygardyn.com/security/> updated.

### 2026-04-09
Filed consumer data access request with Gardyn Inc. Gardyn Privacy Team acknowledged receipt the same day and confirmed processing under the New Jersey Data Privacy Act based on residency.

### 2026-04-09
SecurityWeek updated its 2026-02-27 article to reflect CISA Update A, adding a note that the researcher also identified exposure of partial payment card information: ["Critical Flaws Exposed Gardyn Smart Gardens to Remote Hacking"](https://www.securityweek.com/critical-flaws-exposed-gardyn-smart-gardens-to-remote-hacking/).

### 2026-04-13
Received correspondence from outside counsel at Clark Hill LLP representing Gardyn Inc. in connection with this matter.

### 2026-04-25
Filed supplement to NJDPA right-to-know request with Gardyn Privacy Team referencing the April 9, 2026 acknowledgment and the approximate May 24, 2026 statutory response deadline.

### 2026-04-25
Filed supplement to consumer complaint referred to NJ Division of Consumer Affairs from the New York Office of the Attorney General.

### 2026-04-25
Reviewed publicly available state attorney general breach notification databases for California, Maine, Maryland, Texas, Vermont, and New Jersey. No breach notification by Gardyn Inc. found in any reviewed database as of this date.

## Federal Record Observations

### Per ICSA-26-055-03 Update A — vendor admission on access logging
CISA's published advisory states that the vendor reported to CISA that no access logging existed on the affected endpoints during the exposure window.

### Affected scope per ICSA-26-055-03 Update A — CVE-2026-28766
CVE-2026-28766 (CVSS 9.3) documents an unauthenticated endpoint that returned approximately 134,215 user records including names, email addresses, phone numbers, and last four digits of payment cards.
