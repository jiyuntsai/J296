# Markdown Assignment Data Diary

* [Part One](https://github.com/jiyuntsai/JOURN_296/blob/main/fec.md#part-one): Documenting the steps of cleaning the "Dataset_SOFT100K_95-96.csv" dataset. </br>
* More data and information *[here](https://www.fec.gov/data/)*. </br>
* [Part Two](https://github.com/jiyuntsai/JOURN_296-Data-Journalism/blob/main/fec.md#part-two): Descriptive statistics and answering questions provided by the instructor.
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
* There were 383 donations to the two parties within 1995 and 1996, the total amount of money was $48,502,578, 44.44% ($21,553,578) to Democrat, and 55.56% ($26,949,000) was to Republican. <br/>
![image 1, Sum amount of parties](https://github.com/jiyuntsai/JOURN_296/blob/main/1.png)
* There were 185 donations to Democrat and 198 donations to Republican. Among all, NY state had the most donation events as well as the amount of donation, followed by DC, CA, FL, and MI. However, TX had the 5th most donation events but the amount of money was 7th most. <br/>
![image 2, Count of parties donation](https://github.com/jiyuntsai/JOURN_296/blob/main/2.png)
* The amount of donation got higher in 1996 and **thrived in April 1996** and **thrived again in October 1996** (right before the Novemeber 53rd Presidential Election). <br/>
*Steps: copy the spreadsheet to a new sheet. Copy column "date" and paste to a new colum "Month" then change format to only month+year. Then find a new column to count the total donation for each month (two parties together. can do seperate ones to make a three-line line chart, **Okie I also did this...but I deleted the December 1996 data for this chart because I want to focus on the time before November election**). Use the "=SUMIF" function to sum the total amount of money for each month. Draw a line chart.* <br/>
![image 3, Sum amount of month donation](https://github.com/jiyuntsai/JOURN_296/blob/main/3.png)
![image 9, Sum amount of month donation two line](https://github.com/jiyuntsai/JOURN_296/blob/main/9.png)
* For the Democrat, they received the most times of donation from "Finance, Insurance & Real Estate" sector as well as "Misc Business" sector both had 33 times of donation. And for the amount of money, Democrat received the most from "Finance, Insurance & Real Estate" followed by "Misc Business." For the Republican, they received the most times of donation from "Finance, Insurance & Real Estate" sector for 54 times, followed by "Misc Business" sector for 32 times. As for the amount of money, they received the most from "Finance, Insurance & Real Estate" followed by "Ideological/Single-Issue." However, there was no donation from "Labor" and "Lawyers & Lobbyists" sections. <br/>
![image 4, Count of section parties](https://github.com/jiyuntsai/JOURN_296/blob/main/4.png)

**Assignment Questions** <br/>
1. **Which industries contributed the most to the Republican and Democratic parties? How much was contributed to each party?**
* For the Democratic party, "Media/Entertainment" had the most donation counts, and also contributed the largest amount of money with a $1,880,000 in total. For the Republican, "Securities & Investment" had the most donation counts, but the "Republican/Conservative" contributed the most amount of money, with a $4,939,000 in total. Overall, the Democratic received a $21,553,578 in total and Republican received a $26,949,000 in total. <br/>
![image 5, Sum amount of parties](https://github.com/jiyuntsai/JOURN_296/blob/main/5.png)
* Steps: Set the pivot table with "Industry" in rows, "Party" in columns, and "CountA of Donor" and "Sum of Amount" in values. Voila! Then copy the pivot table and paste the value-only to a blank sheet, delete the first useless row and set the filter for the column-name row. Then according to the questions above, sort the values to see the amount of money and the highest contributions of each industry. <br/>
![image 6, Industry count of parties](https://github.com/jiyuntsai/JOURN_296/blob/main/6.png)

2. **How much did donors from the Misc. Business sector contribute to the Democratic party? Which donors were based in Miami Lakes, FL?**

* Donors from the "Misc. Business" sector contributed a $3,520,000 in total to the Democratic party. And in the sector, Windmere Corp was based in Miami Lakes, FL, and had contributed two times with a $200,000 in total. <br/>
![image 7, Sector amount of parties](https://github.com/jiyuntsai/JOURN_296/blob/main/7.png)
* Steps: Set the pivot table with "Sector" in rows, "Party" in columns, and "Sum of Amount" in values. Voila! Then to see which donors were based in Miami, FL, go back to the original sheet, filter "Party" to only D, "Sector" to only Misc Business, "City" to Miami Lakes, "State" to FL. The answers will be filtered out. <br/>
![image 8, Windmere Corp](https://github.com/jiyuntsai/JOURN_296/blob/main/8.png)

3. **What percentage of the tobacco industry’s donations does Philip Morris account for? How much is it?**

* Philip Morris of the tobacco industry contributed $1,820,000 in total. The total amount of donation in tobacco industry was $2,570,000, so Philip Morris account 70.82% of the industry's donation.

* Steps: Go to the original spreadsheet and filter only "Tobacco" industry. Then you can either do it on the original sheet but I prefer copy the filtered data and paste value-only to another blank sheet. Here you'll get the total amount of donation ($2,570,000) this industry had by using "=SUM" function. Then add all the Philip Morris' donations using the same function, or simply "+" them all to get the total amount of money, which is $1,820,000. Now you can find the percentage by division: 1820000/2570000 then change it to percentage. The answer is 70.82%. *There are many ways to answer this question.*

4. **Describe (in two to three sentences — no need for a detailed story pitch) one potential story from this dataset that you’d find promising if this were a project you were working on. Give it a headline. Include up to three types of sources you would call to report out the story and a few of the questions you might ask. (These can be bullet points — no need for a long explanation.) Remember to detail the steps you took in analyzing the data to get to the story idea. Use the skills we’ve learned to help you.**

* Headline: What happened in June? Republican received 1.1M from Finance, Insurance & Real Estate. <br/>
* Three sources to include: I would include interview with a professional of politics, someone who knows the sector well, and someone from the Republican campaign team in order to figure out why there was huge donation gap between the two parties in June 1996 and why the Republican received large donation from the sector. <br/>
    Questions: <br/>
  * Politics Professions: Were there different strategies for the two parties at the last few months of the election? What were the reasons that cuased the gap of receiving donations in June 1996? <br/>
  * Finance Professions: For the 1996 elections, what kind of campaign promises did the financial groups need? Why do the finance, insurance & real estate support the Republican more? <br/>
  * Republican Team: At the last stage of the election, where did the donation be used on? Did the team focus more on Finance sector for their supports? In which states did the party focus more on? <br/>
* Steps: First made a chart ([image 9](https://github.com/jiyuntsai/JOURN_296/blob/main/9.png)) to see the sum of amount two parties received each month from 1995 to 1996 (I delete the December 1996 data) and I found out that there are two times where donation raised high but the June 1996 looks interesting because Republican received a lot more donation while Democrats' donation dropped in total. To look at it more closely, I use the pivot table, rows for sector, columns for parties, values for the sum of amount, then set the filter for only June 1996. <br/>
![image 10, June 1996 donation](https://github.com/jiyuntsai/JOURN_296/blob/main/10.png)

5. **What data might be suitable to join with this data to provide context or additional stories? Give me two examples.**

* What kind of "promises" did the two parties made in each stage of election to win the support from all sectors. Was there any big economic or finance incident or event happened in the peak of the large amount of donation in June 1996. As the current data we have, adding states and the city might be helpful as well, so that we can see at the last few months of the election, which states did the two parties pay more attention in. Also, compare with the final election result would be good as well, looking at the swing states and the "five flipped states."
