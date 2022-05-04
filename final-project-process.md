# Final Project Data Diary

* [Part One](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-one): Documenting the steps of cleaning the dataset.
* [Part Two](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-two): Descriptive statistics and story ideas.
* Access .csv dataset: [Original](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/Business_Licenses(original).csv) and [Cleaned](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/Business_Licenses(cleaned).csv)
* Read Final Project Story *[here](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-story.md)*. <br/>
<!-- I am sooooooooo tirrrrrrrrrrred bruhhhhhhhhhhh-->

### About this data <br/>
>This is a dataset of registered businesses in the City of Berkeley with business license records <br/>
Dataset: [Business_Licenses](https://data.cityofberkeley.info/Business/Business-Licenses/rwnf-bu3w) <br/>
Source: City of Berkeley Finance Department <br/>
Dates Covered: Daily update, dataset exported on April 26, 2022 <br/>
More information of City of Berkeley Open Data *[here](https://data.cityofberkeley.info/)* <br/>

### Dataset Description <br/>
>RecordID: License number, unique <br/>
Minority_Owned: Indicates whether business is minority owned <br/>
Female_Owned: Indicates whether business is female owned <br/>
B1_PER_SUB_TYPE: Record type for internal classification <br/>
Bus_Own_Type: Type of business ownership structure (i.e. corporation, LLC, sole-ownership, etc) <br/>
Full description *[here](https://drive.google.com/file/d/1Ou8U6Q6X_qIdRvASN8QyvPVrcwdVKSVw/view?usp=sharing)* <br/>

## Part One

**Import dataset to a new google [spreadsheet](https://docs.google.com/spreadsheets/d/1SH9cntqwLkngYWbZ1HqiDEozQgJiCJI6Bqzv9l7l_vs/edit?usp=sharing)(view mode).** <br/>

**Clean Data**
1. Freeze the first row and make the first row **Bold**.
2. Trim Whitespace: Data >> Data cleanup, trim all whitespaces. (cleared!)
3. Create Filters: easier to sort specific things.
4. Check values of Column "Minority_Owned" and "Female_Owned", see if there's value other than "YES", "NO" and "(Blank)". (cleared!)
5. Check "RecordID": each id should be unique. (Found one duplicated one!) Delete row 2200 with id "BL-006880".
6. Column "B1_ZIP" and "B1_SITUS_ZIP": City of Berkeley uses zipcodes 94701-94710, 94712, and 94720 (94701 and 94712 are PO Box, 94720 belongs to UC Berkeley). Filtered out values other than 94702-94710 and 94720: <br/>
&nbsp;* BL-000283: "B1_ZIP" change from "947041521" to "94704-1521" and fill in the physical address data after searching online. <br/>
&nbsp;* BL-002285: "B1_SITUS_ZIP" change from "94701" to "94710" along with the change of "Business_Location". <br/>
&nbsp;* BL-004576, BL-006880, BL-023239, BL-023507, BL-023969, BL-047847, BL-047849, BL-053103: add physical address. <br/>
&nbsp;* BL-007121: "B1_SITUS_ZIP" change from "94701" to "94710" along with the change of "Business_Location". <br/>
&nbsp;* BL-053103: "B1_SITUS_ZIP" change from "94701" to "94704" along with the change of "Business_Location". <br/>
7. Check column "B1_FULL_ADDRESS" too: <br/>
&nbsp;* BL-003236, BL-003291, BL-006330: add physical address. <br/>

**Noted** <br/>
Business_Location: If shows "0 Various" then business is located elsewhere but operates in Berkeley without a physical location, need to filter out when mapping.

## Part Two

**Data Processing** <br/>
Create pivot table: Insert >> Pivot table >> Create New Sheet <br/>

**Descriptive Statistics** <br/>
1. Of all the 12760 businesses, 2382 businesses (18.67%) indicade themselves female-owned businesses. <br/>
&nbsp;* Pivot table set columns to "Female_Owned" and values to "RecordID" (show as both Default and % of row) <br/>
![image 1, pivot table of indicading female-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp1.png) <br/>

2. Of all the 12760 businesses, 1799 businesses (14.10%) indicade themselves minority-owned businesses. <br/>
&nbsp;* Pivot table set columns to "Minority_Owned" and values to "RecordID" (show as both Default and % of row) <br/>
![image 2, pivot table of indicading minority-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp2.png) <br/>

3. 39.29% of female-owned businesses indicade themselves minority-owned businesses. <br/>
&nbsp;* Pivot table set filters to "Female_Owned" (status showing "YES"), columns to "Minority_Owned", and values to "RecordID" (show as both Default and % of row) <br/>
![image 3, pivot table of indicading female-owned and minority-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp3.png) <br/>

4. For female-owned businesses, most businesses are sole-ownership. But for non-female-owned businesses, corporation has the most count. <br/>
&nbsp;* Pivot table set rows to "Female_Owned", columns to "Bus_Own_Type", and values to "RecordID" (show as % of grand total) <br/>
&nbsp;* *LLC: Limited liability company*
![image 4, pivot table of business owned type by indicating female-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp4.png) <br/>

5. Among all business, "Rental of Real Property" is the largest business type. The second largest is "Construction or contractor" followed by "Professional SemiProfessional" category. <br/>
&nbsp;* Pivot table set rows to "Female_Owned", columns to "B1_PER_SUB_TYPE", and values to "RecordID" (show as Default, % of row, and % of grand total) then, copy and paste value-only to another sheet <br/>
![image 5, tables of large business type among all businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp5.png) <br/>

6. For female-owned businesses, "Rental of Real Property" is the largest business type, followed by "Professional SemiProfessional", "Retail Trade", and "Business Personal Repair Svs". <br/>
&nbsp;* Pivot table set rows to "Female_Owned", columns to "B1_PER_SUB_TYPE", and values to "RecordID" (show as Default and % of row) then, copy and paste value-only to another sheet <br/>
![image 6, tables of large business type among female-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp6.png) <br/>

7. However, for non-female-owned businesses, "Construction or contractor" is the largest business type, followed by "Rental of Real Property" and  "Professional SemiProfessional". <br/>
&nbsp;* Pivot table set rows to "Female_Owned", columns to "B1_PER_SUB_TYPE", and values to "RecordID" (show as Default and % of row) then, copy and paste value-only to another sheet. For table with counted values, add up rows of "blank" and "NO" and name this row with "NON-female-owned" and remame row "YES" to "female-owned". Then, for table with % of row values, divide "NON-female-owned" values by total "NON-female-owned" to calculate the percentage. Finally, copy and paste value-only to that row <br/>
![image 7, tables of large business type among non-female-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp7.png) <br/>

**Find the Story** <br/>
After browsing the dataset and running some descriptive statistics, I am curious about **what the businesses around UC Berkeley looks like**. So I tried different ways to determine the definition of "around UC Berkeley campus" and finally decided to use zipcodes of 94704 and 94709 that cover the "north shattuck", "downtown", and "telegraph avenue district" neighborhoods that surround the UC Berkeley campus. <br/>
So I filtered out "0 VARIOUS " of column "B1_FULL_ADDRESS" and then filter "B1_SITUS_ZIP" to show zipcodes of only 94704 and 94709. <br/> 
And here's the descriptive statistic of businesses around UC Berkeley:
![image 8, tables of businesses type around UC Berkeley campus](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp8.png) <br/>

**Identify Sources** <br/>
1. Beth Roessner, CEO, Berkeley Chamber of Commerce, [Women Entrepreneurs of Berkeley (WEB)](https://web.berkeleychamber.com/WEB-Member-Directory)
2. Kathy, Landlord in North Berkeley
3. City of Berkeley, [Economic Dashboards and Reports](https://berkeleyca.gov/doing-business/economic-development/economic-dashboards-and-reports)
4. Berkeley Rent Board, [Data and Reports](https://rentboard.berkeleyca.gov/forms-reports/data-reports)
