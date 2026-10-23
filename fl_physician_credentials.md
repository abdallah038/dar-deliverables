# Florida Physician Credential Verification — Five MDs, Hillsborough County, FL

Observation of public records only; no contact with any third party, no emails, calls or messages.
Carried out unattended by an autonomous agent (DAR Studio 2); no human performed any step.

## 1. Credential Table

| # | NPI | Name as printed in NPPES | NPPES enumeration date | Primary taxonomy code / description | Practice address city | Florida licence | Licence type | Licence status | Original issue date | Expiration date | DOH discipline / public complaint |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 1013935618 | TONI ANITA MITCHELL | 2006-07-18 | 207R00000X / Internal Medicine | TAMPA, FL 336074156 | ME40152 | Medical Doctor | Clear/Active | 07/01/1982 | 1/31/2028 | Discipline on File: No; Public Complaint: No |
| 2 | 1164535670 | ADELA M OLIVA | 2006-08-17 | 207R00000X / Internal Medicine | BRANDON, FL 335112801 | ME36107 | Medical Doctor | Clear/Active | 03/18/1980 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 3 | 1295798619 | RICHARD LANDRIGAN | 2006-04-07 | 208800000X / Urology | BRANDON, FL 335115985 | ME35858 | Medical Doctor | Clear/Active | 12/18/1979 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 4 | 1841283710 | STEPHEN M ZWEIBACH | 2005-08-25 | 207V00000X / Obstetrics & Gynecology | BRANDON, FL 335115707 | ME34836 | Medical Doctor | Clear/Active | 07/02/1979 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 5 | 1366451684 | JAMES V. HILLMAN | 2006-08-05 | 207P00000X / Emergency Medicine | TAMPA, FL 336131367 | ME32771 | Medical Doctor | Clear/Active | 08/02/1978 | 1/31/2028 | Discipline on File: No; Public Complaint: No |

## 2. Cross-Check

| # | NPPES name | DOH name | Name match | NPPES practice address | DOH address of record | Address match | OIG LEIE result |
|---|---|---|---|---|---|---|---|
| 1 | TONI ANITA MITCHELL | TONI ANITA MITCHELL | match | 4200 W CYPRESS ST, TAMPA, FL 336074156 | 818 Chipaway Drive APOLLO BEACH, FL 33572 | mismatch (city: NPPES prints TAMPA, DOH prints APOLLO BEACH) | not found for this physician (the search returned a different individual, MITCHELL, TONIA MICHELLE; see excerpt) |
| 2 | ADELA M OLIVA | ADELA M OLIVA | match | 1439 OAKFIELD DR, BRANDON, FL 335112801 | 904 tomahawk trail Brandon Florida BRANDON, FL 33511 | match | not found (No Results were found) |
| 3 | RICHARD LANDRIGAN | RICHARD ROY LANDRIGAN MD | mismatch (DOH prints RICHARD ROY LANDRIGAN MD) | 505 EICHENFELD DR, BRANDON, FL 335115985 | 505 EICHENFELD DRIVE SUITE 109 BRANDON, FL 33511 | match | not found (No Results were found) |
| 4 | STEPHEN M ZWEIBACH | STEPHEN MARK ZWEIBACH | mismatch (DOH prints STEPHEN MARK ZWEIBACH) | 204 OAKFIELD DR, BRANDON, FL 335115707 | 204 Oakfield Drive BRANDON BRANDON, FL 33511 | match | not found (No Results were found) |
| 5 | JAMES V. HILLMAN | JAMES V HILLMAN MD | mismatch (DOH prints JAMES V HILLMAN MD) | 16002 LAKESHORE VILLA DR, TAMPA, FL 336131367 | 119 Oakfield Dr BRANDON, FL 33511 | mismatch (city: NPPES prints TAMPA, DOH prints BRANDON) | not found (No Results were found) |

## 3. Summary

- verified clean (active licence, no discipline, no public complaint, not on LEIE): **5**
- name mismatches between NPPES and DOH: **3**
- address mismatches between NPPES and DOH: **2**
- licences expiring within 90 days of the retrieval time (retrieval 2026-10-23; +90d = 2027-01-21): **0** — the five expiration dates are 1/31/2028 (1) and 1/31/2027 (4), all after 2027-01-21
- OIG LEIE exclusions for these five physicians: **0** (four 'No Results were found'; one search returned a different individual with the same surname)

## 4. Sources

Every query below is listed with its own exact query URL or form fields, its own UTC retrieval time,
and a verbatim raw excerpt of 10-30 lines pasted inside this file.

### 4.0 Florida DOH MQA practitioner search (the query that selected the five physicians)

- source: Florida Department of Health MQA Practitioner Profile Search (official)
- form fields: POST https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/PractitionerProfileSearch with `__RequestVerificationToken=<session token>`,
  `SearchDto.Board=15` (Board of Medicine), `SearchDto.Profession=1501` (Medical Doctor),
  `SearchDto.County=HILLSBOROUGH`, all other fields empty
- UTC retrieval time: 2026-10-23T00:16:39Z

```text
Search Results Total: 8654
Export
Back New Search
License
Name
Profession
City
County
Zip Code
License Status
38144
DAYAL, BHAWAN
Medical Doctor
******
HILLSBOROUGH
*****
Deceased
38813
SUSLAVICH, FRANK JOHN
Medical Doctor
BRANDON
HILLSBOROUGH
33509-0861
Vol Relinquish
5833
DAVIS, ROBERT J
Medical Doctor
BRANDON
HILLSBOROUGH
33510-2902
```

### 4.1 Physician 1 — TONI ANITA MITCHELL

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1013935618
- UTC retrieval time: 2026-10-23T00:16:22Z

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
- UTC retrieval time: 2026-10-23T00:09:07Z

```text
TONI ANITA MITCHELL
License Number: ME40152
Data As Of 10/22/2026
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
- UTC retrieval time: 2026-10-23T00:16:40Z (the page prints "10/22/2026 8:16:44 PM EST on OIG LEIE Exclusions database."; the LEIE server clock is US Eastern, and the recorded server time at the call is the UTC time given here)

```text
Exclusions Search Results:
Individuals
Results were found for MITCHELL, TONI
If the name of the individual or entity appears below, click on the underlined last name or entity name to Verify the record. If the name does not appear in the search results below, print this Web page for your documentation.
Last Name First Name Middle Name General Specialty Exclusion Waiver SSN/EIN
MITCHELL
TONIA
MICHELLE
SKILLED NURSING FAC
SOCIAL WORKER
1128(a)(2)
Verify
Search conducted 10/22/2026 8:16:44 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
About OIG
About Us
About the Inspector General
Organization Chart
Careers
Reports & Publications
All Reports & Publications
Archives
Fraud
```

### 4.2 Physician 2 — ADELA M OLIVA

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1164535670
- UTC retrieval time: 2026-10-23T00:16:24Z

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
- UTC retrieval time: 2026-10-23T00:09:08Z

```text
ADELA M OLIVA
License Number: ME36107
Data As Of 10/22/2026
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
- UTC retrieval time: 2026-10-23T00:16:42Z (the page prints "10/22/2026 8:16:46 PM EST on OIG LEIE Exclusions database."; the LEIE server clock is US Eastern, and the recorded server time at the call is the UTC time given here)

```text
Exclusions Search Results:
Individuals
No Results were found for OLIVA , ADELA
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/22/2026 8:16:46 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
About OIG
About Us
About the Inspector General
Organization Chart
Careers
Reports & Publications
All Reports & Publications
Archives
Fraud
Report Fraud
Medical ID Theft/Fraud Information
Medicaid Fraud Control Units - MFCUs
Enforcement Actions
State False Claims Act Reviews
Most-Wanted Fugitives
```

### 4.3 Physician 3 — RICHARD LANDRIGAN

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1295798619
- UTC retrieval time: 2026-10-23T00:16:25Z

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
- UTC retrieval time: 2026-10-23T00:09:10Z

```text
RICHARD ROY LANDRIGAN MD
License Number: ME35858
Data As Of 10/22/2026
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
- UTC retrieval time: 2026-10-23T00:16:44Z (the page prints "10/22/2026 8:16:48 PM EST on OIG LEIE Exclusions database."; the LEIE server clock is US Eastern, and the recorded server time at the call is the UTC time given here)

```text
Exclusions Search Results:
Individuals
No Results were found for LANDRIGAN , RICHARD
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/22/2026 8:16:48 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
About OIG
About Us
About the Inspector General
Organization Chart
Careers
Reports & Publications
All Reports & Publications
Archives
Fraud
Report Fraud
Medical ID Theft/Fraud Information
Medicaid Fraud Control Units - MFCUs
Enforcement Actions
State False Claims Act Reviews
Most-Wanted Fugitives
```

### 4.4 Physician 4 — STEPHEN M ZWEIBACH

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1841283710
- UTC retrieval time: 2026-10-23T00:16:27Z

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
- UTC retrieval time: 2026-10-23T00:09:12Z

```text
STEPHEN MARK ZWEIBACH
License Number: ME34836
Data As Of 10/22/2026
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
- UTC retrieval time: 2026-10-23T00:16:46Z (the page prints "10/22/2026 8:16:50 PM EST on OIG LEIE Exclusions database."; the LEIE server clock is US Eastern, and the recorded server time at the call is the UTC time given here)

```text
Exclusions Search Results:
Individuals
No Results were found for ZWEIBACH , STEPHEN
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/22/2026 8:16:50 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
About OIG
About Us
About the Inspector General
Organization Chart
Careers
Reports & Publications
All Reports & Publications
Archives
Fraud
Report Fraud
Medical ID Theft/Fraud Information
Medicaid Fraud Control Units - MFCUs
Enforcement Actions
State False Claims Act Reviews
Most-Wanted Fugitives
```

### 4.5 Physician 5 — JAMES V. HILLMAN

**NPPES NPI Registry**

- query URL: https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1366451684
- UTC retrieval time: 2026-10-23T00:16:29Z

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
- UTC retrieval time: 2026-10-23T00:09:14Z

```text
JAMES V HILLMAN MD
License Number: ME32771
Data As Of 10/22/2026
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
- UTC retrieval time: 2026-10-23T00:16:48Z (the page prints "10/22/2026 8:16:52 PM EST on OIG LEIE Exclusions database."; the LEIE server clock is US Eastern, and the recorded server time at the call is the UTC time given here)

```text
Exclusions Search Results:
Individuals
No Results were found for HILLMAN , JAMES
If no results are found, this individual or
entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation
Search Again
Search conducted 10/22/2026 8:16:52 PM EST on OIG LEIE Exclusions database.
Source data updated on 10/9/2026 10:01:00 AM EST
Return to Search
About OIG
About Us
About the Inspector General
Organization Chart
Careers
Reports & Publications
All Reports & Publications
Archives
Fraud
Report Fraud
Medical ID Theft/Fraud Information
Medicaid Fraud Control Units - MFCUs
Enforcement Actions
State False Claims Act Reviews
Most-Wanted Fugitives
```
