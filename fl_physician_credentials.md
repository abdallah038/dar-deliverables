# Florida Physician Credential Verification — Five MDs, Hillsborough County, FL

> **Observation of public records only.** This work retrieved data exclusively from the three named public registries (CMS NPPES NPI Registry, Florida DOH MQA Practitioner Profile Search, HHS-OIG LEIE). No emails, calls, messages, posts or account creation were performed, and nothing was submitted to Synmerco.

**Intent:** `c9242e6d-e413-46b7-9b86-6d8da1b0cca7`  
**Retrieval time (UTC):** `2026-10-22T23:39:09Z`  
**Sources:** CMS NPPES NPI Registry (npiregistry.cms.hhs.gov) · Florida DOH MQA (mqa-internet.doh.state.fl.us) · HHS-OIG LEIE (exclusions.oig.hhs.gov)

---

## 1. Credential Table

| # | NPI | Name (as printed in NPPES) | NPPES enumeration date | Primary taxonomy code | Primary taxonomy description | Practice city (NPPES LOCATION) | Florida licence number | Licence type | Licence status | Original issue date | Expiration date | DOH discipline / public complaint |
|---|-----|----------------------------|------------------------|-----------------------|------------------------------|-------------------------------|------------------------|--------------|----------------|--------------------|-----------------|----------------------------------|
| 1 | 1013935618 | TONI MITCHELL | 2006-07-18 | 207R00000X | Internal Medicine | TAMPA | ME40152 | Medical Doctor | Clear/Active | 07/01/1982 | 1/31/2028 | Discipline on File: No; Public Complaint: No |
| 2 | 1164535670 | ADELA OLIVA | 2006-08-17 | 207R00000X | Internal Medicine | BRANDON | ME36107 | Medical Doctor | Clear/Active | 03/18/1980 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 3 | 1295798619 | RICHARD LANDRIGAN | 2006-04-07 | 208800000X | Urology | BRANDON | ME35858 | Medical Doctor | Clear/Active | 12/18/1979 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 4 | 1841283710 | STEPHEN ZWEIBACH | 2005-08-25 | 207V00000X | Obstetrics & Gynecology | BRANDON | ME34836 | Medical Doctor | Clear/Active | 07/02/1979 | 1/31/2027 | Discipline on File: No; Public Complaint: No |
| 5 | 1366451684 | JAMES HILLMAN | 2006-08-05 | 207P00000X | Emergency Medicine | TAMPA | ME32771 | Medical Doctor | Clear/Active | 08/02/1978 | 1/31/2028 | Discipline on File: No; Public Complaint: No |

## 2. Cross-Check

| # | Physician | Name match (NPPES vs DOH) | Address match (NPPES LOCATION vs DOH Address of Record) | Differing field | OIG LEIE result |
|---|-----------|---------------------------|--------------------------------------------------------|----------------|-----------------|
| 1 | MITCHELL | Match — NPPES 'TONI MITCHELL' (middle ANITA) vs DOH 'TONI ANITA MITCHELL' | Mismatch | City/street: NPPES LOCATION '4200 W CYPRESS ST, TAMPA FL 33607' vs DOH '818 Chipaway Drive, APOLLO BEACH, FL 33572' | Search returned a result row for 'MITCHELL, TONIA MICHELLE' (SOCIAL WORKER, SKILLED NURSING FAC, exclusion type 1128(a)(2)) — a different individual, not this physician |
| 2 | OLIVA | Match — NPPES 'ADELA OLIVA' (middle M) vs DOH 'ADELA M OLIVA' | Mismatch | Street: NPPES LOCATION '1439 OAKFIELD DR, BRANDON FL 33511' vs DOH '904 tomahawk trail Brandon, BRANDON, FL 33511' | not found |
| 3 | LANDRIGAN | Match — NPPES 'RICHARD LANDRIGAN' vs DOH 'RICHARD ROY LANDRIGAN MD' | Match | Same street/city/zip: NPPES '505 EICHENFELD DR, BRANDON FL 33511' vs DOH '505 EICHENFELD DRIVE SUITE 109, BRANDON, FL 33511' (DOH adds suite) | not found |
| 4 | ZWEIBACH | Match — NPPES 'STEPHEN ZWEIBACH' (middle M) vs DOH 'STEPHEN MARK ZWEIBACH' | Match | Same street/city/zip: NPPES '204 OAKFIELD DR, BRANDON FL 33511' vs DOH '204 Oakfield Drive, BRANDON, FL 33511' | not found |
| 5 | HILLMAN | Match — NPPES 'JAMES HILLMAN' (middle V.) vs DOH 'JAMES V HILLMAN MD' | Mismatch | City/street: NPPES LOCATION '16002 LAKESHORE VILLA DR, TAMPA FL 33613' vs DOH '119 Oakfield Dr, BRANDON, FL 33511' | not found |

## 3. Summary

| Metric | Count | Arithmetic |
|--------|-------|------------|
| Physicians verified | 5 | 5 selected |
| Active Florida licence (Clear/Active) | 5 | 5 of 5 |
| Verified clean (active licence + DOH Discipline on File = No + DOH Public Complaint = No + no LEIE exclusion for that person) | 5 | 5 of 5 |
| NPPES↔DOH name mismatches | 0 | 0 of 5 |
| NPPES↔DOH address mismatches | 3 | MITCHELL, OLIVA, HILLMAN |
| Licences expiring within 90 days of retrieval | 0 | retrieval 2026-10-22 + 90 d = 2027-01-20; expirations 1/31/2027 (×3) and 1/31/2028 (×2), all after 2027-01-20 |
| LEIE exclusions for these physicians | 0 | 4 'not found'; 1 result row for a different individual (MITCHELL, TONIA MICHELLE) |

**Fields the sources did not print**

- The DOH Practitioner Profile page prints `Year Began Practicing` but does **not** print an `Original Issue Date`; the `Original Issue Date` was obtained from the DOH **License Verification** page (`/MQASearchServices/HealthCareProviders/LicenseVerification`), a separate page linked from the profile's `License Information` tab.
- The DOH search results page masks city/zip as `******` for Deceased/Retired records; the five selected physicians are `Clear/Active` and print normally.
- NPPES `basic.name` is `null` for all five records; the name is assembled from `basic.first_name` / `basic.middle_name` / `basic.last_name`.
- The DOH record prints `Profession` = `Medical Doctor`; it does not print a separate licence `type` string.
- The DOH profile page does not print a `Public Complaint` indicator; that field appears only on the License Verification page.

## 4. Sources

Every query run is listed with its exact URL/form fields, UTC retrieval time, and a verbatim raw excerpt.

### 4.0 Florida DOH MQA — practitioner search query

- **Source:** Florida DOH MQA Practitioner Profile Search (mqa-internet.doh.state.fl.us)
- **Method:** GET then POST to `https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/PractitionerProfileSearch`
- **Form fields:** `__RequestVerificationToken=<session token>`, `SearchDto.Board=15` (BOARD OF MEDICINE), `SearchDto.Profession=1501` (Medical Doctor), `SearchDto.County=HILLSBOROUGH`, `SearchDto.LastName=`, `SearchDto.FirstName=`, `SearchDto.City=`, `SearchDto.ZipCode=`, `SearchDto.LicenseNumber=`, `SearchDto.SpecialtyOrCertification=`, `SearchDto.OtherSpecialtyOrCertification=`
- **Result:** `Search Results Total: 8654`
- **Retrieval time (UTC):** `2026-10-22T23:39:09Z`

```html
<h2> Practitioner Profile Search</h2>

<form action="/MQASearchServices/HealthCareProviders/PractitionerProfileSearch" method="post">        <p>
            Sort by selecting column header.</p>
        <table class="table table-striped table-condensed table-hover">
            <caption class="caption" style="text-align: left;">
                Search Results Total: 8654
                <span style="float: right; margin-right: 5px;"><a class="btn btn-primary btn-sm" href="/MQASearchServices/HealthCareProviders/ExportToCsvPP?jsonModel=%7B%22Id%22%3A0%2C%22Board%22%3A%2215%22%2C%22Profession%22%3A%221501%22%2C%22SpecialtyOrCertification%22%3Anull%2C%22OtherSpecialtyOrCertification%22%3Anull%2C%22LicenseNumber%22%3Anull%2C%22FirstName%22%3Anull%2C%22LastName%22%3Anull%2C%22BusinessName%22%3Anull%2C%22City%22%3Anull%2C%22County%22%3A%22HILLSBOROUGH%22%2C%22ZipCode%22%3Anull%2C%22LicenseStatus%22%3Anull%2C%22IsAuthorizedToOrderCannabis%22%3Anull%7D">Export</a></span>
                <span style="float: right; margin-right: 5px;"><button class="btn btn-primary btn-sm" onclick="window.history.go(-1); return false;">Back</button> <a class="btn btn-primary btn-sm" href="/MQASearchServices/HealthCareProviders/PractitionerProfileSearch">New Search</a></span>

            </caption>
            <thead>
            <tr>
                <th class="header-sort" onclick="location.href = '/MQASearchServices/HealthCareProviders/IndexSortedPractitioner?fieldToSort=1'">
                    License

                </th>
                <th class="header-sort" onclick="location.href = '/MQASearchServices/HealthCareProviders/IndexSortedPractitioner?fieldToSort=2'">
                    Name

                </th>
                <th class="header-sort" onclick="location.href = '/MQASearchServices/HealthCareProviders/IndexSortedPractitioner?fieldToSort=3'">
                    Profession

                </th>
                <th class="header-sort" onclick="location.href = '/MQASearchServices/HealthCareProviders/IndexSortedPractitioner?fieldToSort=4'">
                    City

                </th>
                <th class="header-sort" onclick="location.href = '/MQASearchServices/HealthCareProviders/IndexSortedPractitioner?fieldToSort=5'">
                    County
```

### 4.1 Physician 1: TONI MITCHELL (NPI 1013935618, FL licence ME40152)

**NPPES excerpt** — `GET https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1013935618` — retrieval `2026-10-22T23:39:09Z`
```json
{
 "result_count": 1,
 "results": [
  {
   "addresses": [
    {
     "address_1": "4200 W CYPRESS ST",
     "address_purpose": "MAILING",
     "address_type": "DOM",
     "city": "TAMPA",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-314-2045",
     "postal_code": "336074156",
     "state": "FL",
     "telephone_number": "813-830-6905"
    },
    {
     "address_1": "4200 W CYPRESS ST",
     "address_purpose": "LOCATION",
     "address_type": "DOM",
     "city": "TAMPA",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-314-2045",
     "postal_code": "336074156",
     "state": "FL",
     "telephone_number": "813-830-6905"
    }
   ],
```

**DOH excerpt (License Verification page)** — `GET https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=32144&ProCde=1501` — retrieval `2026-10-22T23:39:09Z`
```html

        <dt>
            License
        </dt>
        <dd>
            ME40152
        </dd>

        <!-- Covid 19 change-->
            <!-- regular license status display-->
            <dt>
                <a href=https://flhealthsource.gov/files/License%20Status%20Descriptions.pdf target="_blank" class="icon glyphicon glyphicon-question-sign" style="color:#00A0AF;"></a>
                License Status
            </dt>
            <dd>
                Clear/Active

            </dd>

        

                <dt>
                    
License Expiration Date                </dt>
                <dd>
1/31/2028                </dd>
                <dt>
                    License Original Issue Date
                </dt>
            <dd>
```

**DOH excerpt (License Verification page — address & discipline)** — same URL — retrieval `2026-10-22T23:39:09Z`
```html
                    <dt>
                    </dt>
                    <dd>
                        APOLLO BEACH, FL 33572
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        
                    </dd>
                    <dt>
                        <a data-toggle="modal" data-target="#ControlledSubstance" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"> </a>
                        Controlled Substance Prescriber 
(for the Treatment of Chronic Non-malignant Pain)
                    </dt>
                    <dd>
                        <span>Yes</span>
                    </dd>
                    <dt>
                        Discipline on File
                    </dt>
                    <dd>
                            <span>No</span>
                    </dd>
                        <dt>
                            <a data-toggle="modal" data-target="#PublicComplaint" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"></a>
                            Public Complaint
                        </dt>
                        <dd>
                                <span>No</span>
```

**LEIE excerpt** — `POST https://exclusions.oig.hhs.gov/` with form fields `ctl00$cpExclusions$txtSPLastName=MITCHELL`, `ctl00$cpExclusions$txtSPFirstName=TONI`, `__EVENTTARGET=ctl00$cpExclusions$ibSearchSP` → results page `https://exclusions.oig.hhs.gov/SearchResults.aspx` — retrieval `2026-10-22T23:39:09Z`
```html

        <p><span id="ctl00_cpExclusions_lblSearchData">Results were found for <ul><li>MITCHELL, TONI</li></ul></span>

                </p __designer:mapid="6d3">

                

                

                

                <p id="ctl00_cpExclusions_P2">

                    <img src="images/icon_norecord.gif" id="ctl00_cpExclusions_img1" alt="Not Excluded" style="vertical-align: -2px; margin-right: 5px;" />

                    <strong style="font-size: 13px;">If the name of the individual or entity appears below, click on the underlined last name or entity name to Verify the record. If the name does not appear in the search results below, print this Web page for your documentation.</strong>

					

					</p>

					

    </div>

    

</div>

     
```

**LEIE excerpt (results table / timestamp)** — same query — retrieval `2026-10-22T23:39:09Z`
```html

					<td>

                        <a id="ctl00_cpExclusions_gvEmployees_ctl02_cmdVerify" href="javascript:__doPostBack(&#39;ctl00$cpExclusions$gvEmployees$ctl02$cmdVerify&#39;,&#39;&#39;)">MITCHELL</a>

                    </td><td>TONIA</td><td>MICHELLE</td><td>SKILLED NURSING FAC</td><td>SOCIAL WORKER</td><td> 1128(a)(2)</td><td>                    

                         

                    </td><td>

                        <a id="ctl00_cpExclusions_gvEmployees_ctl02_cmdVerify2" href="javascript:__doPostBack(&#39;ctl00$cpExclusions$gvEmployees$ctl02$cmdVerify2&#39;,&#39;&#39;)" style="color:Blue;">Verify</a>

                    </td>

				</tr>

			</table>

		</div>        

                    

                </td>

	</tr>

</table>

     
```

**LEIE excerpt (search timestamp)** — same query — retrieval `2026-10-22T23:39:09Z`
```html

	

            <div class="timeStampResults" style="margin-top:20px;">

                <p><span id="ctl00_cpExclusions_lblDatabaseDateTime">Search conducted 10/22/2026 7:47:22 PM EST on OIG LEIE Exclusions database. <br>Source data updated on 10/9/2026 10:01:00 AM EST</span></p>

            </div>

        
```

### 4.2 Physician 2: ADELA OLIVA (NPI 1164535670, FL licence ME36107)

**NPPES excerpt** — `GET https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1164535670` — retrieval `2026-10-22T23:39:09Z`
```json
{
 "result_count": 1,
 "results": [
  {
   "addresses": [
    {
     "address_1": "1439 OAKFIELD DR",
     "address_purpose": "MAILING",
     "address_type": "DOM",
     "city": "BRANDON",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-654-1722",
     "postal_code": "335112801",
     "state": "FL",
     "telephone_number": "813-689-2853"
    },
    {
     "address_1": "1439 OAKFIELD DR",
     "address_purpose": "LOCATION",
     "address_type": "DOM",
     "city": "BRANDON",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-654-1722",
     "postal_code": "335112801",
     "state": "FL",
     "telephone_number": "813-689-2853"
    }
   ],
```

**DOH excerpt (License Verification page)** — `GET https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=28245&ProCde=1501` — retrieval `2026-10-22T23:39:09Z`
```html

        <dt>
            License
        </dt>
        <dd>
            ME36107
        </dd>

        <!-- Covid 19 change-->
            <!-- regular license status display-->
            <dt>
                <a href=https://flhealthsource.gov/files/License%20Status%20Descriptions.pdf target="_blank" class="icon glyphicon glyphicon-question-sign" style="color:#00A0AF;"></a>
                License Status
            </dt>
            <dd>
                Clear/Active

            </dd>

        

                <dt>
                    
License Expiration Date                </dt>
                <dd>
1/31/2027                </dd>
                <dt>
                    License Original Issue Date
                </dt>
            <dd>
```

**DOH excerpt (License Verification page — address & discipline)** — same URL — retrieval `2026-10-22T23:39:09Z`
```html
                    <dt>
                    </dt>
                    <dd>
                        BRANDON, FL 33511
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        
                    </dd>
                    <dt>
                        <a data-toggle="modal" data-target="#ControlledSubstance" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"> </a>
                        Controlled Substance Prescriber 
(for the Treatment of Chronic Non-malignant Pain)
                    </dt>
                    <dd>
                        <span>Yes</span>
                    </dd>
                    <dt>
                        Discipline on File
                    </dt>
                    <dd>
                            <span>No</span>
                    </dd>
                        <dt>
                            <a data-toggle="modal" data-target="#PublicComplaint" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"></a>
                            Public Complaint
                        </dt>
                        <dd>
                                <span>No</span>
```

**LEIE excerpt** — `POST https://exclusions.oig.hhs.gov/` with form fields `ctl00$cpExclusions$txtSPLastName=OLIVA`, `ctl00$cpExclusions$txtSPFirstName=ADELA`, `__EVENTTARGET=ctl00$cpExclusions$ibSearchSP` → results page `https://exclusions.oig.hhs.gov/SearchResults.aspx` — retrieval `2026-10-22T23:39:09Z`
```html

                <p><span id="ctl00_cpExclusions_lblMessage">No Results were found for <ul><li> OLIVA , ADELA </li></ul></span>

                </p __designer:mapid="6d6">

                <p id="ctl00_cpExclusions_P1">

                    <img src="images/icon_norecord.gif" id="ctl00_cpExclusions_imgNoRecord" alt="Not Excluded" style="vertical-align: -2px; margin-right: 5px;" />

                    <strong style="font-size: 13px;">If no results are found, this individual or 

                    entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation</strong>

					

					</p>

					<p>

                    <a id="ctl00_cpExclusions_lbGridBackToSearch" class="single_multiple" href="javascript:__doPostBack(&#39;ctl00$cpExclusions$lbGridBackToSearch&#39;,&#39;&#39;)">Search Again</a>

					</p>

					

            </div>

        

</div>
```

**LEIE excerpt (results table / timestamp)** — same query — retrieval `2026-10-22T23:39:09Z`
```html

	

            <div class="timeStampResults" style="margin-top:20px;">

                <p><span id="ctl00_cpExclusions_lblDatabaseDateTime">Search conducted 10/22/2026 7:47:24 PM EST on OIG LEIE Exclusions database. <br>Source data updated on 10/9/2026 10:01:00 AM EST</span></p>

            </div>

        
```

### 4.3 Physician 3: RICHARD LANDRIGAN (NPI 1295798619, FL licence ME35858)

**NPPES excerpt** — `GET https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1295798619` — retrieval `2026-10-22T23:39:09Z`
```json
{
 "result_count": 1,
 "results": [
  {
   "addresses": [
    {
     "address_1": "505 EICHENFELD DR",
     "address_2": "SUITE 109",
     "address_purpose": "MAILING",
     "address_type": "DOM",
     "city": "BRANDON",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-689-0825",
     "postal_code": "335115985",
     "state": "FL",
     "telephone_number": "813-684-0808"
    },
    {
     "address_1": "505 EICHENFELD DR",
     "address_2": "SUITE 109",
     "address_purpose": "LOCATION",
     "address_type": "DOM",
     "city": "BRANDON",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-689-0825",
     "postal_code": "335115985",
     "state": "FL",
     "telephone_number": "813-684-0808"
```

**DOH excerpt (License Verification page)** — `GET https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=28011&ProCde=1501` — retrieval `2026-10-22T23:39:09Z`
```html

        <dt>
            License
        </dt>
        <dd>
            ME35858
        </dd>

        <!-- Covid 19 change-->
            <!-- regular license status display-->
            <dt>
                <a href=https://flhealthsource.gov/files/License%20Status%20Descriptions.pdf target="_blank" class="icon glyphicon glyphicon-question-sign" style="color:#00A0AF;"></a>
                License Status
            </dt>
            <dd>
                Clear/Active

            </dd>

        

                <dt>
                    
License Expiration Date                </dt>
                <dd>
1/31/2027                </dd>
                <dt>
                    License Original Issue Date
                </dt>
            <dd>
```

**DOH excerpt (License Verification page — address & discipline)** — same URL — retrieval `2026-10-22T23:39:09Z`
```html
                    <dt>
                    </dt>
                    <dd>
                        BRANDON, FL 33511
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        
                    </dd>
                    <dt>
                        <a data-toggle="modal" data-target="#ControlledSubstance" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"> </a>
                        Controlled Substance Prescriber 
(for the Treatment of Chronic Non-malignant Pain)
                    </dt>
                    <dd>
                        <span>No</span>
                    </dd>
                    <dt>
                        Discipline on File
                    </dt>
                    <dd>
                            <span>No</span>
                    </dd>
                        <dt>
                            <a data-toggle="modal" data-target="#PublicComplaint" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"></a>
                            Public Complaint
                        </dt>
                        <dd>
                                <span>No</span>
```

**LEIE excerpt** — `POST https://exclusions.oig.hhs.gov/` with form fields `ctl00$cpExclusions$txtSPLastName=LANDRIGAN`, `ctl00$cpExclusions$txtSPFirstName=RICHARD`, `__EVENTTARGET=ctl00$cpExclusions$ibSearchSP` → results page `https://exclusions.oig.hhs.gov/SearchResults.aspx` — retrieval `2026-10-22T23:39:09Z`
```html

                <p><span id="ctl00_cpExclusions_lblMessage">No Results were found for <ul><li> LANDRIGAN , RICHARD </li></ul></span>

                </p __designer:mapid="6d6">

                <p id="ctl00_cpExclusions_P1">

                    <img src="images/icon_norecord.gif" id="ctl00_cpExclusions_imgNoRecord" alt="Not Excluded" style="vertical-align: -2px; margin-right: 5px;" />

                    <strong style="font-size: 13px;">If no results are found, this individual or 

                    entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation</strong>

					

					</p>

					<p>

                    <a id="ctl00_cpExclusions_lbGridBackToSearch" class="single_multiple" href="javascript:__doPostBack(&#39;ctl00$cpExclusions$lbGridBackToSearch&#39;,&#39;&#39;)">Search Again</a>

					</p>

					

            </div>

        

</div>
```

**LEIE excerpt (results table / timestamp)** — same query — retrieval `2026-10-22T23:39:09Z`
```html

	

            <div class="timeStampResults" style="margin-top:20px;">

                <p><span id="ctl00_cpExclusions_lblDatabaseDateTime">Search conducted 10/22/2026 7:47:25 PM EST on OIG LEIE Exclusions database. <br>Source data updated on 10/9/2026 10:01:00 AM EST</span></p>

            </div>

        
```

### 4.4 Physician 4: STEPHEN ZWEIBACH (NPI 1841283710, FL licence ME34836)

**NPPES excerpt** — `GET https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1841283710` — retrieval `2026-10-22T23:39:09Z`
```json
{
 "result_count": 1,
 "results": [
  {
   "addresses": [
    {
     "address_1": "PO BOX 741436",
     "address_purpose": "MAILING",
     "address_type": "DOM",
     "city": "ATLANTA",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "866-346-1426",
     "postal_code": "303741436",
     "state": "GA",
     "telephone_number": "615-373-7600"
    },
    {
     "address_1": "204 OAKFIELD DR",
     "address_purpose": "LOCATION",
     "address_type": "DOM",
     "city": "BRANDON",
     "country_code": "US",
     "country_name": "United States",
     "fax_number": "813-688-9890",
     "postal_code": "335115707",
     "state": "FL",
     "telephone_number": "813-688-9888"
    }
   ],
```

**DOH excerpt (License Verification page)** — `GET https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=27275&ProCde=1501` — retrieval `2026-10-22T23:39:09Z`
```html

        <dt>
            License
        </dt>
        <dd>
            ME34836
        </dd>

        <!-- Covid 19 change-->
            <!-- regular license status display-->
            <dt>
                <a href=https://flhealthsource.gov/files/License%20Status%20Descriptions.pdf target="_blank" class="icon glyphicon glyphicon-question-sign" style="color:#00A0AF;"></a>
                License Status
            </dt>
            <dd>
                Clear/Active

            </dd>

        

                    <dt>
                        <a data-toggle="modal" data-target="#SingleMutliStateLicense" style="color: #00A0AF; display:none;" class="icon glyphicon glyphicon-question-sign"></a>
                        Qualifications
                    </dt>
                    <dd>
                        Dispensing Practitioner
                    </dd>
                <dt>
                    
```

**DOH excerpt (License Verification page — address & discipline)** — same URL — retrieval `2026-10-22T23:39:09Z`
```html
                        
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        BRANDON
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        BRANDON, FL 33511
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        
                    </dd>
                    <dt>
                        <a data-toggle="modal" data-target="#ControlledSubstance" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"> </a>
                        Controlled Substance Prescriber 
(for the Treatment of Chronic Non-malignant Pain)
                    </dt>
                    <dd>
                        <span>Yes</span>
                    </dd>
                    <dt>
                        Discipline on File
                    </dt>
                    <dd>
                            <span>No</span>
```

**LEIE excerpt** — `POST https://exclusions.oig.hhs.gov/` with form fields `ctl00$cpExclusions$txtSPLastName=ZWEIBACH`, `ctl00$cpExclusions$txtSPFirstName=STEPHEN`, `__EVENTTARGET=ctl00$cpExclusions$ibSearchSP` → results page `https://exclusions.oig.hhs.gov/SearchResults.aspx` — retrieval `2026-10-22T23:39:09Z`
```html

                <p><span id="ctl00_cpExclusions_lblMessage">No Results were found for <ul><li> ZWEIBACH , STEPHEN </li></ul></span>

                </p __designer:mapid="6d6">

                <p id="ctl00_cpExclusions_P1">

                    <img src="images/icon_norecord.gif" id="ctl00_cpExclusions_imgNoRecord" alt="Not Excluded" style="vertical-align: -2px; margin-right: 5px;" />

                    <strong style="font-size: 13px;">If no results are found, this individual or 

                    entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation</strong>

					

					</p>

					<p>

                    <a id="ctl00_cpExclusions_lbGridBackToSearch" class="single_multiple" href="javascript:__doPostBack(&#39;ctl00$cpExclusions$lbGridBackToSearch&#39;,&#39;&#39;)">Search Again</a>

					</p>

					

            </div>

        

</div>
```

**LEIE excerpt (results table / timestamp)** — same query — retrieval `2026-10-22T23:39:09Z`
```html

	

            <div class="timeStampResults" style="margin-top:20px;">

                <p><span id="ctl00_cpExclusions_lblDatabaseDateTime">Search conducted 10/22/2026 7:47:27 PM EST on OIG LEIE Exclusions database. <br>Source data updated on 10/9/2026 10:01:00 AM EST</span></p>

            </div>

        
```

### 4.5 Physician 5: JAMES HILLMAN (NPI 1366451684, FL licence ME32771)

**NPPES excerpt** — `GET https://npiregistry.cms.hhs.gov/api/?version=2.1&number=1366451684` — retrieval `2026-10-22T23:39:09Z`
```json
{
 "result_count": 1,
 "results": [
  {
   "addresses": [
    {
     "address_1": "34 LADOGA AVE",
     "address_purpose": "MAILING",
     "address_type": "DOM",
     "city": "TAMPA",
     "country_code": "US",
     "country_name": "United States",
     "postal_code": "336063804",
     "state": "FL",
     "telephone_number": "813-251-8515"
    },
    {
     "address_1": "16002 LAKESHORE VILLA DR",
     "address_purpose": "LOCATION",
     "address_type": "DOM",
     "city": "TAMPA",
     "country_code": "US",
     "country_name": "United States",
     "postal_code": "336131367",
     "state": "FL",
     "telephone_number": "813-968-5093"
    }
   ],
   "basic": {
    "credential": "M.D.",
```

**DOH excerpt (License Verification page)** — `GET https://mqa-internet.doh.state.fl.us/MQASearchServices/HealthCareProviders/LicenseVerification?LicInd=25284&ProCde=1501` — retrieval `2026-10-22T23:39:09Z`
```html
        </dd>

        <dt>
            License
        </dt>
        <dd>
            ME32771
        </dd>

        <!-- Covid 19 change-->
            <!-- regular license status display-->
            <dt>
                <a href=https://flhealthsource.gov/files/License%20Status%20Descriptions.pdf target="_blank" class="icon glyphicon glyphicon-question-sign" style="color:#00A0AF;"></a>
                License Status
            </dt>
            <dd>
                Clear/Active

            </dd>

        

                <dt>
                    
License Expiration Date                </dt>
                <dd>
1/31/2028                </dd>
                <dt>
                    License Original Issue Date
                </dt>
```

**DOH excerpt (License Verification page — address & discipline)** — same URL — retrieval `2026-10-22T23:39:09Z`
```html
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        BRANDON, FL 33511
                    </dd>
                    <dt>
                    </dt>
                    <dd>
                        
                    </dd>
                    <dt>
                        <a data-toggle="modal" data-target="#ControlledSubstance" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"> </a>
                        Controlled Substance Prescriber 
(for the Treatment of Chronic Non-malignant Pain)
                    </dt>
                    <dd>
                        <span>Yes</span>
                    </dd>
                    <dt>
                        Discipline on File
                    </dt>
                    <dd>
                            <span>No</span>
                    </dd>
                        <dt>
                            <a data-toggle="modal" data-target="#PublicComplaint" style="color: #00A0AF;" class="icon glyphicon glyphicon-question-sign"></a>
                            Public Complaint
                        </dt>
                        <dd>
```

**LEIE excerpt** — `POST https://exclusions.oig.hhs.gov/` with form fields `ctl00$cpExclusions$txtSPLastName=HILLMAN`, `ctl00$cpExclusions$txtSPFirstName=JAMES`, `__EVENTTARGET=ctl00$cpExclusions$ibSearchSP` → results page `https://exclusions.oig.hhs.gov/SearchResults.aspx` — retrieval `2026-10-22T23:39:09Z`
```html

                <p><span id="ctl00_cpExclusions_lblMessage">No Results were found for <ul><li> HILLMAN , JAMES </li></ul></span>

                </p __designer:mapid="6d6">

                <p id="ctl00_cpExclusions_P1">

                    <img src="images/icon_norecord.gif" id="ctl00_cpExclusions_imgNoRecord" alt="Not Excluded" style="vertical-align: -2px; margin-right: 5px;" />

                    <strong style="font-size: 13px;">If no results are found, this individual or 

                    entity (if it is an entity search) is not currently excluded. Print this Web page for your documentation</strong>

					

					</p>

					<p>

                    <a id="ctl00_cpExclusions_lbGridBackToSearch" class="single_multiple" href="javascript:__doPostBack(&#39;ctl00$cpExclusions$lbGridBackToSearch&#39;,&#39;&#39;)">Search Again</a>

					</p>

					

            </div>

        

</div>
```

**LEIE excerpt (results table / timestamp)** — same query — retrieval `2026-10-22T23:39:09Z`
```html

	

            <div class="timeStampResults" style="margin-top:20px;">

                <p><span id="ctl00_cpExclusions_lblDatabaseDateTime">Search conducted 10/22/2026 7:47:29 PM EST on OIG LEIE Exclusions database. <br>Source data updated on 10/9/2026 10:01:00 AM EST</span></p>

            </div>

        
```
