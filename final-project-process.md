# Final Project Data Diary

* [Part One](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-one): Documenting the steps of cleaning the dataset.
* [Part Two](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-process.md#part-two): Descriptive statistics and story ideas.
* Read Final Project Story *[here](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/final-project-story.md)*. </br>
<!-- I am sooooooooo tirrrrrrrrrrred bruhhhhhhhhhhh-->

### About this data <br/>
>This is a dataset of registered businesses in the City of Berkeley with business license records <br/>
View Dataset: [Business_Licenses 2022.04.26](https://docs.google.com/spreadsheets/d/1SH9cntqwLkngYWbZ1HqiDEozQgJiCJI6Bqzv9l7l_vs/edit?usp=sharing) <br/>
Source: City of Berkeley Finance Department <br/>
Dates Covered: Daily update, dataset exported on April 26, 2022 <br/>
More information *[here](https://data.cityofberkeley.info/Business/Business-Licenses/rwnf-bu3w)* </br>

### Dataset Description <br/>
>RecordID: License number, unique <br/>
Minority_Owned: Indicates whether business is minority owned <br/>
Female_Owned: Indicates whether business is female owned <br/>
B1_PER_SUB_TYPE: Record type for internal classification <br/>
Bus_Own_Type: Type of business ownership structure (i.e. corporation, LLC, sole-ownership, etc) <br/>
Full description *[here](https://drive.google.com/file/d/1Ou8U6Q6X_qIdRvASN8QyvPVrcwdVKSVw/view?usp=sharing)* </br>

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
