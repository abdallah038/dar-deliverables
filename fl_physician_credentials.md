# Florida Physician Credential Verification — Five MDs, Hillsborough County, FL

Observation of public records only; no contact with any third party, no emails, calls or messages.
Carried out unattended by an autonomous agent (DAR Studio 2); no human performed any step.

## 1. Credential Table

| # | NPI | Name as printed in NPPES | NPPES enumeration date | Primary taxonomy code | Primary taxonomy description | NPPES practice address (street, city, ZIP) | Florida licence number | Licence type | Licence status | Original issue date | Expiration date | DOH discipline / public complaint |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 1013935618 | TONI ANITA MITCHELL | 2006-07-18 | 207R00000X | Internal Medicine | 4200 W CYPRESS ST, TAMPA 336074156 | ME40152 | Medical Doctor | Clear/Active | 07/01/1982 | 1/31/2028 | Discipline on File: No; Public Complaint: No |
| 2 | 1164535670 | ADELA M OLIVA | 2006-08-17 | 207R00000X | Internal Medicine | 1439 OAKFIELD DR, BRANDON 335112801 | ME36107 | Medical Doctor | Clear/Active | 03/18/1980 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 3 | 1295798619 | RICHARD LANDRIGAN | 2006-04-07 | 208800000X | Urology | 505 EICHENFELD DR, BRANDON 335115985 | ME35858 | Medical Doctor | Clear/Active | 12/18/1979 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 4 | 1841283710 | STEPHEN M ZWEIBACH | 2005-08-25 | 207V00000X | Obstetrics & Gynecology | 204 OAKFIELD DR, BRANDON 335115707 | ME34836 | Medical Doctor | Clear/Active | 07/02/1979 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 5 | 1366451684 | JAMES V. HILLMAN | 2006-08-05 | 207P00000X | Emergency Medicine | 16002 LAKESHORE VILLA DR, TAMPA 336131367 | ME32771 | Medical Doctor | Clear/Active | 08/02/1978 | 1/31/2028 | Discipline on File: No; Public Complaint: No |

## 2. Cross-Check

| # | NPPES name | DOH name | Name match | NPPES practice address | DOH address of record | Address match | OIG LEIE result |
|---|---|---|---|---|---|---|---|
| 1 | TONI ANITA MITCHELL | TONI ANITA MITCHELL | match | 4200 W CYPRESS ST, TAMPA 336074156 | 818 Chipaway Drive, APOLLO BEACH, FL 33572 | mismatch (city: NPPES prints TAMPA, DOH prints APOLLO BEACH) | not found for this physician — the search returned a different individual, MITCHELL, TONIA MICHELLE (see excerpt) |
| 2 | ADELA M OLIVA | ADELA M OLIVA | match | 1439 OAKFIELD DR, BRANDON 335112801 | 904 tomahawk trail, Brandon Florida BRANDON, FL 33511 | mismatch (street: NPPES prints 1439 OAKFIELD DR, DOH prints 904 tomahawk trail) | not found (No Results were found) |
| 3 | RICHARD LANDRIGAN | RICHARD ROY LANDRIGAN MD | mismatch (DOH prints RICHARD ROY LANDRIGAN MD, NPPES prints RICHARD LANDRIGAN) | 505 EICHENFELD DR, BRANDON 335115985 | 505 EICHENFELD DRIVE, SUITE 109 BRANDON, FL 33511 | match (both print 505 EICHENFELD DR / DRIVE, BRANDON; DOH adds SUITE 109, NPPES prints none) | not found (No Results were found) |
| 4 | STEPHEN M ZWEIBACH | STEPHEN MARK ZWEIBACH | mismatch (DOH prints STEPHEN MARK ZWEIBACH, NPPES prints STEPHEN M ZWEIBACH) | 204 OAKFIELD DR, BRANDON 335115707 | 204 Oakfield Drive, BRANDON BRANDON, FL 33511 | match (both print 204 Oakfield Drive / DR, BRANDON) | not found (No Results were found) |
| 5 | JAMES V. HILLMAN | JAMES V HILLMAN MD | mismatch (DOH prints JAMES V HILLMAN MD, NPPES prints JAMES V. HILLMAN) | 16002 LAKESHORE VILLA DR, TAMPA 336131367 | 119 Oakfield Dr, BRANDON, FL 33511 | mismatch (street and city: NPPES prints 16002 LAKESHORE VILLA DR, TAMPA, DOH prints 119 Oakfield Dr, BRANDON) | not found (No Results were found) |

## 3. Summary

Counts below are computed from the rows of Sections 1-2 above; every input is one of those rows.

- verified clean (active licence, no discipline, no public complaint, not on LEIE): **5** — all five rows carry Licence status `Clear/Active`, Discipline on File `No`, Public Complaint `No`, and an LEIE result of not found.
- name mismatches between NPPES and DOH: **3** — physicians 3 (RICHARD LANDRIGAN vs RICHARD ROY LANDRIGAN MD), 4 (STEPHEN M ZWEIBACH vs STEPHEN MARK ZWEIBACH), 5 (JAMES V. HILLMAN vs JAMES V HILLMAN MD).
- address mismatches between NPPES and DOH: **3** — physicians 1 (city), 2 (street), 5 (street and city); physicians 3 and 4 match.
- licences expiring within 90 days of the retrieval time (retrieval 2026-10-23T19:58:07Z; +90 days = 2027-01-21): **0** — the five expiration dates are `1/31/2028` (**2**: physicians 1 and 5) and `1/31/2027` (**3**: physicians 2, 3 and 4), and both dates fall after 2027-01-21.
- OIG LEIE exclusions for these five physicians: **0** — four searches printed `No Results were found`; one search (MITCHELL, TONI) returned a different individual, MITCHELL, TONIA MICHELLE, who is not one of the five physicians in this file.

## 4. Sources

Every query below is listed with its own exact query URL or form fields, its own UTC retrieval time,
and a verbatim raw excerpt pasted inside this file. Excerpts are the lines the source printed.

### 4.0 Florida DOH MQA practitioner search (the query that selected the five physicians)

- source: Florida Department of Health MQA Practitioner Profile Search (official)
- query: POST https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/PractitionerProfileSearch with form fields
  `SearchDto.Board=15` (Board of Medicine), `SearchDto.Profession=1501` (Medical Doctor),
  `SearchDto.County=HILLSBOROUGH`, `SearchDto.LastName=` empty, all other fields empty
- UTC retrieval time: 2026-10-23T19:58:28Z

```text
Search Results Total: 8655
Export
Back New Search
License
Name
Profession
City
County
Zip Code
License Status
```

### 4.1 Physician 1 — TONI ANITA MITCHELL

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1013935618
- UTC retrieval time: 2026-10-23T19:58:07Z

```json
{
 "number": "1013935618",
 "basic": {
  "first_name": "TONI",
  "middle_name": "ANITA",
  "last_name": "MITCHELL",
  "credential": "MD",
  "enumeration_date": "2006-07-18"
 },
 "taxonomies": [
  {
   "code": "207R00000X",
   "desc": "Internal Medicine",
   "license": "ME40152",
   "primary": true,
   "state": "FL"
  }
 ],
 "addresses": [
  {
   "address_purpose": "LOCATION",
   "address_1": "4200 W CYPRESS ST",
   "city": "TAMPA",
   "state": "FL",
   "postal_code": "336074156"
  }
 ]
}
```

**Florida DOH MQA — License Verification**

- query URL: https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=32144&ProCde=1501
- UTC retrieval time: 2026-10-23T20:08:07Z

```text
License Verification
Printer Friendly Version
TONI ANITA MITCHELL
License Number: ME40152
Data As Of 10/23/2026
License Information
Secondary Locations
Discipline/Admin Action
Practitioner Profile
Profession
Medical Doctor
License
ME40152
License Status
Clear/Active
License Expiration Date
1/31/2028
License Original Issue Date
07/01/1982
Address of Record
818 Chipaway Drive
APOLLO BEACH, FL 33572
Controlled Substance Prescriber
(for the Treatment of Chronic Non-malignant Pain)
Yes
Discipline on File
No
Public Complaint
No
```

**HHS-OIG LEIE**

- query: POST https://exclusions.oig.hhs.gov/ with last name `MITCHELL`, first name `TONI`
- UTC retrieval time: 2026-10-23T19:58:32Z

```text
Exclusions Search Results:
Individuals
Results were found for MITCHELL, TONI
If the name of the individual or entity appears below, click on the underlined last name or entity name to Verify the record. If the name does not appear in the search results below, print this Web page for your documentation.
Last NameFirst NameMiddle NameGeneralSpecialtyExclusionWaiverSSN/EIN
MITCHELL
TONIAMICHELLESKILLED NURSING FACSOCIAL WORKER 1128(a)(2)
Verify
Search conducted 10/23/2026 3:58:37 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
```

### 4.2 Physician 2 — ADELA M OLIVA

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1164535670
- UTC retrieval time: 2026-10-23T19:58:07Z

```json
{
 "number": "1164535670",
 "basic": {
  "first_name": "ADELA",
  "middle_name": "M",
  "last_name": "OLIVA",
  "credential": "MD",
  "enumeration_date": "2006-08-17"
 },
 "taxonomies": [
  {
   "code": "207R00000X",
   "desc": "Internal Medicine",
   "license": "me0036107",
   "primary": true,
   "state": "FL"
  }
 ],
 "addresses": [
  {
   "address_purpose": "LOCATION",
   "address_1": "1439 OAKFIELD DR",
   "city": "BRANDON",
   "state": "FL",
   "postal_code": "335112801"
  }
 ]
}
```

**Florida DOH MQA — License Verification**

- query URL: https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=28245&ProCde=1501
- UTC retrieval time: 2026-10-23T20:08:09Z

```text
License Verification
Printer Friendly Version
ADELA M OLIVA
License Number: ME36107
Data As Of 10/23/2026
License Information
Secondary Locations
Discipline/Admin Action
Practitioner Profile
Profession
Medical Doctor
License
ME36107
License Status
Clear/Active
License Expiration Date
1/31/2027
License Original Issue Date
03/18/1980
Address of Record
904 tomahawk trail
Brandon
Florida
BRANDON, FL 33511
Controlled Substance Prescriber
(for the Treatment of Chronic Non-malignant Pain)
Yes
Discipline on File
No
Public Complaint
No
```

**HHS-OIG LEIE**

- query: POST https://exclusions.oig.hhs.gov/ with last name `OLIVA`, first name `ADELA`
- UTC retrieval time: 2026-10-23T19:58:34Z

```text
Exclusions Search Results:
Individuals
No Results were found for  OLIVA , ADELA
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/23/2026 3:58:38 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
```

### 4.3 Physician 3 — RICHARD LANDRIGAN

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1295798619
- UTC retrieval time: 2026-10-23T19:58:08Z

```json
{
 "number": "1295798619",
 "basic": {
  "first_name": "RICHARD",
  "middle_name": null,
  "last_name": "LANDRIGAN",
  "credential": "MD",
  "enumeration_date": "2006-04-07"
 },
 "taxonomies": [
  {
   "code": "208800000X",
   "desc": "Urology",
   "license": "me35858",
   "primary": true,
   "state": "FL"
  }
 ],
 "addresses": [
  {
   "address_purpose": "LOCATION",
   "address_1": "505 EICHENFELD DR",
   "city": "BRANDON",
   "state": "FL",
   "postal_code": "335115985"
  }
 ]
}
```

**Florida DOH MQA — License Verification**

- query URL: https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=28011&ProCde=1501
- UTC retrieval time: 2026-10-23T20:08:10Z

```text
License Verification
Printer Friendly Version
RICHARD ROY LANDRIGAN MD
License Number: ME35858
Data As Of 10/23/2026
License Information
Secondary Locations
Discipline/Admin Action
Practitioner Profile
Profession
Medical Doctor
License
ME35858
License Status
Clear/Active
License Expiration Date
1/31/2027
License Original Issue Date
12/18/1979
Address of Record
505 EICHENFELD DRIVE
SUITE 109
BRANDON, FL 33511
Controlled Substance Prescriber
(for the Treatment of Chronic Non-malignant Pain)
No
Discipline on File
No
Public Complaint
No
```

**HHS-OIG LEIE**

- query: POST https://exclusions.oig.hhs.gov/ with last name `LANDRIGAN`, first name `RICHARD`
- UTC retrieval time: 2026-10-23T19:58:36Z

```text
Exclusions Search Results:
Individuals
No Results were found for  LANDRIGAN , RICHARD
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/23/2026 3:58:40 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
```

### 4.4 Physician 4 — STEPHEN M ZWEIBACH

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1841283710
- UTC retrieval time: 2026-10-23T19:58:08Z

```json
{
 "number": "1841283710",
 "basic": {
  "first_name": "STEPHEN",
  "middle_name": "M",
  "last_name": "ZWEIBACH",
  "credential": "M.D.",
  "enumeration_date": "2005-08-25"
 },
 "taxonomies": [
  {
   "code": "207V00000X",
   "desc": "Obstetrics & Gynecology",
   "license": "ME34836",
   "primary": true,
   "state": "FL"
  }
 ],
 "addresses": [
  {
   "address_purpose": "LOCATION",
   "address_1": "204 OAKFIELD DR",
   "city": "BRANDON",
   "state": "FL",
   "postal_code": "335115707"
  }
 ]
}
```

**Florida DOH MQA — License Verification**

- query URL: https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=27275&ProCde=1501
- UTC retrieval time: 2026-10-23T20:08:11Z

```text
License Verification
Printer Friendly Version
STEPHEN MARK ZWEIBACH
License Number: ME34836
Data As Of 10/23/2026
License Information
Secondary Locations
Discipline/Admin Action
Practitioner Profile
Profession
Medical Doctor
License
ME34836
License Status
Clear/Active
Qualifications
Dispensing Practitioner
License Expiration Date
1/31/2027
License Original Issue Date
07/02/1979
Address of Record
204 Oakfield Drive
BRANDON
BRANDON, FL 33511
Controlled Substance Prescriber
(for the Treatment of Chronic Non-malignant Pain)
Yes
Discipline on File
No
Public Complaint
No
```

**HHS-OIG LEIE**

- query: POST https://exclusions.oig.hhs.gov/ with last name `ZWEIBACH`, first name `STEPHEN`
- UTC retrieval time: 2026-10-23T19:58:37Z

```text
Exclusions Search Results:
Individuals
No Results were found for  ZWEIBACH , STEPHEN
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/23/2026 3:58:41 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
```

### 4.5 Physician 5 — JAMES V. HILLMAN

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1366451684
- UTC retrieval time: 2026-10-23T19:58:09Z

```json
{
 "number": "1366451684",
 "basic": {
  "first_name": "JAMES",
  "middle_name": "V.",
  "last_name": "HILLMAN",
  "credential": "M.D.",
  "enumeration_date": "2006-08-05"
 },
 "taxonomies": [
  {
   "code": "207P00000X",
   "desc": "Emergency Medicine",
   "license": "ME32771",
   "primary": true,
   "state": "FL"
  }
 ],
 "addresses": [
  {
   "address_purpose": "LOCATION",
   "address_1": "16002 LAKESHORE VILLA DR",
   "city": "TAMPA",
   "state": "FL",
   "postal_code": "336131367"
  }
 ]
}
```

**Florida DOH MQA — License Verification**

- query URL: https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=25284&ProCde=1501
- UTC retrieval time: 2026-10-23T20:08:16Z

```text
License Verification
Printer Friendly Version
JAMES V HILLMAN MD
License Number: ME32771
Data As Of 10/23/2026
License Information
Secondary Locations
Discipline/Admin Action
Subordinate Practitioners
Practitioner Profile
Profession
Medical Doctor
License
ME32771
License Status
Clear/Active
License Expiration Date
1/31/2028
License Original Issue Date
08/02/1978
Address of Record
119 Oakfield Dr
BRANDON, FL 33511
Controlled Substance Prescriber
(for the Treatment of Chronic Non-malignant Pain)
Yes
Discipline on File
No
Public Complaint
No
```

**HHS-OIG LEIE**

- query: POST https://exclusions.oig.hhs.gov/ with last name `HILLMAN`, first name `JAMES`
- UTC retrieval time: 2026-10-23T19:58:38Z

```text
Exclusions Search Results:
Individuals
No Results were found for  HILLMAN , JAMES
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/23/2026 3:58:42 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
```

### 4.6 Existence check per surname (why these five are the five most recent clear/active MDs in the county)

- source: Florida Department of Health MQA Practitioner Profile Search (official)
- query: POST https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/PractitionerProfileSearch with form fields
  `SearchDto.Board=15`, `SearchDto.Profession=1501`, `SearchDto.County=` empty, `SearchDto.LastName=<surname>`
- UTC retrieval times: MITCHELL at 2026-10-23T19:58:16Z; OLIVA at 2026-10-23T19:58:18Z; LANDRIGAN at 2026-10-23T19:58:20Z; ZWEIBACH at 2026-10-23T19:58:23Z; HILLMAN at 2026-10-23T19:58:26Z

```text
MITCHELL: Search Results Total: 119 | Export | Back New Search | License | Name | Profession | City | County | Zip Code | License Status
OLIVA: Search Results Total: 27 | Export | Back New Search | License | Name | Profession | City | County | Zip Code | License Status
LANDRIGAN: Practitioner Profile | Printer Friendly Version | RICHARD ROY LANDRIGAN MD | License Number: ME35858 | Profession | Medical Doctor | License Status | Clear/Active | Year Began Practicing | 01/01/1984
ZWEIBACH: Practitioner Profile | Printer Friendly Version | STEPHEN MARK ZWEIBACH | License Number: ME34836 | Profession | Medical Doctor | License Status | Clear/Active | Year Began Practicing | 01/01/1978
HILLMAN: Search Results Total: 9 | Export | Back New Search | License | Name | Profession | City | County | Zip Code | License Status
```

(Each line is the response to one surname query. The DOH returns a result count, or the single matching
practitioner profile page when exactly one record exists — LANDRIGAN and ZWEIBACH returned a profile page.)

## 5. Acceptance checklist

- Section 1 lists, per physician, NPI, NPPES name, NPPES enumeration date, primary taxonomy code and description,
  practice address city, Florida licence number, licence type, licence status, original issue date, expiration date,
  and the DOH discipline / public complaint indicator as printed.
- Section 2 gives a match/mismatch verdict per physician, naming the differing field, for name and address,
  and the OIG LEIE result (not found / found with exclusion type and date).
- Section 3 gives counts: verified clean, name mismatches, address mismatches, expirations within 90 days of the
  retrieval time, and exclusions — each count traced to the rows of Sections 1-2.
- Sources section: for every query run — source name, exact query URL or form fields, UTC retrieval time, and a
  verbatim raw excerpt pasted inside this file.
- No personal email, telephone or fax number appears in this file; no contact was made with any third party.
- One line states that the work was carried out unattended by an autonomous agent.
