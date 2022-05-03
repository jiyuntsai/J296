# Final Project Data Diary

* [Part One](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-one): Documenting the steps of cleaning the dataset.
* [Part Two](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-two): Descriptive statistics and story ideas.
* Read Final Project Story *[here](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-story.md)*. <br/>
<!-- I am sooooooooo tirrrrrrrrrrred bruhhhhhhhhhhh-->

### About this data <br/>
>This is a dataset of registered businesses in the City of Berkeley with business license records <br/>
Dataset: [Business_Licenses](https://data.cityofberkeley.info/Business/Business-Licenses/rwnf-bu3w) <br/>
Source: City of Berkeley Finance Department <br/>
Dates Covered: Daily update, dataset exported on April 26, 2022 <br/>
Access dataset from [repo](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/fpp.csv)
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
&nbsp;* BL-004576: add physical address. <br/>
&nbsp;* BL-006880: add physical address. <br/>
&nbsp;* BL-007121: "B1_SITUS_ZIP" change from "94701" to "94710" along with the change of "Business_Location". <br/>
&nbsp;* BL-023239: add physical address. <br/>
&nbsp;* BL-023507: add physical address. <br/>
&nbsp;* BL-023969: add physical address. <br/>
&nbsp;* BL-047847: add physical address. <br/>
&nbsp;* BL-047849: add physical address. <br/>
&nbsp;* BL-053103: "B1_SITUS_ZIP" change from "94701" to "94704" along with the change of "Business_Location". <br/>

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

3. 39.29% of female-owned businesses indicade themselves minority-owned businesses.
&nbsp;* Pivot table set filters to "Female_Owned" (status showing "YES"), columns to "Minority_Owned", and values to "RecordID" (show as both Default and % of row) <br/>
![image 3, pivot table of indicading female-owned and minority-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp3.png) <br/>

4. For female-owned businesses, most businesses are sole-ownership. But for non-female-owned businesses, corporation has the most count.
&nbsp;* Pivot table set rows to "Female_Owned", columns to "Bus_Own_Type", and values to "RecordID" (show as % of grand total) <br/>
![image 4, pivot table of business owned type by indicating female-owned businesses](https://github.com/jiyuntsai/JOURN_296/blob/main/fpp4.png) <br/>



