# Final Project Data Diary

* [Part One](https://github.com/jiyuntsai/JOURN_296/blob/main/final-project-process.md#part-one): Documenting the steps of cleaning the "Dataset_SOFT100K_95-96.csv" dataset. </br>
* More data and information *[here](https://www.fec.gov/data/)*. </br>
* [Part Two](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-two): Descriptive statistics and answering questions provided by the instructor.
<!-- and Happy President's Day btw! I am writing this assignment on Sunday because I'm going to Napa Valley tomorrow! YABEEE -->
<!-- Crap I still didn't finish it... -->

### About this data <br/>
>This is data provided by the Federal Election Commissions about donations totaling more than $100,000 to the Republican and Democratic entities backing Bill Clinton and Bob Dole’s presidential campaigns. <br/>
File Names: Dataset_SOFT100K_95-96.csv <br/>
Source: Federal Election Commission <br/>
Dates Covered: January 1995 to December 1996 <br/>

### Dataset_SOFT100K_95-96.csv <br/>
>Donor: individual, company or entity that donated money to either campaign
Amount: amount over $100,000 contributed to either campaign <br/>
Date: date of contribution to either campaign <br/>
Recipient: Committee receiving the donation which backs either Bill Clinton or Bob Dole’s presidential campaigns <br/>
Party: designation of the political party, either Republican or Democrat <br/>
Donor's Business or Organization: donor’s business or organizational affiliation <br/>
Sector: sector to which the donor entity belongs or represents <br/>
Industry: industry to which the donor entity belongs or represents <br/>
City: City the donor is based or headquartered  in <br/>
State: State the donor is based or headquartered in <br/>
Zip: ZIP code the donor is based or headquartered in <br/>
***
## Part One

Import dataset to a new google [spreadsheet](https://docs.google.com/spreadsheets/d/1tvC-hINf7kAM-ODnsHkkAQD8c7uTWjtlVfPofsAcVms/edit?usp=sharing)(view mode). <br/>

**Clean Data**
1. Freeze the first row and make the first row **Bold**. <br/>
2. Trim Whitespace: Data >> Data cleanup, trim all whitespace. (cleared!)
3. Duplicate Rows: Data >> Data cleanup, remove all the duplicate rows. There are 15 rows removed.
4. Create Filters: easier to sort specific things.
5. Sort *"Amount"*: make sure all the values are over $100,000. (cleared!)
6. Sort *"Date"*: make sure all the data are within 1995 and 1996. (cleared!)
7. Filter *"Party"*: it should be either Republican or Democrat, according to the dataset description. There are three rows that show "3" and all belong to the "Natural Law Party of the United States" so I decided to **DELETE**. More information of this party *[here](https://docquery.fec.gov/pdf/017/23992183017/23992183017.pdf)*.
8. Filter *"State"*: make sure they are all abbreviation of all 51 states. There is one "PR" which stands for Puerto Rico. (mark red!)
9. Sort *"Zip"*: US zipcodes should always be 5 digits, there are some vlaue that are 3 (belongs to Puerto Rico) or 4 digits only. It might because of the zipcodes start with *0*, to confirm, find out those 4-digit zipcodes and check with the states they belong. Zip Codes in Massachusetts, New Hampshire, Connecticut, New Jersey start with 0, change the format of number to *plain text* add the *0* back.
10. *"Zip"* column also have two missing values, search them online. *"76155"* for American Airline at DALLAS/FORT WORTH and *"10020"* for Johnson Co at New York.
11. City mispellings: check if there's any mispellings in city column.

**Process Data** <br/>
Create pivot table: Insert >> Pivot table

## Part Two

**Descriptive Statistics** <br/>
