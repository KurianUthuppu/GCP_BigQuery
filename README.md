# Google Cloud Platform (GCP) - BigQuery
_Lists out the basic steps towards using Google Cloud Platform (GCP) BigQuery (GCP's SQL platform)
_Very useful to analyze datasets that are large enough (Circa 1 lakh+ cells) to make Google sheets / Microsoft excel hang_

### Requirements
* Valid Google account
* Browser - Chrome / Firefox
* Valid Credit card

### Resources
- GCP platform login - https://cloud.google.com/?authuser=1 ($300 credit for free usage and testing for the first 6 months)
- Helpful Google documentation - https://cloud.google.com/bigquery/docs?authuser=1
- Useful startup video - https://youtu.be/JLXLCv5nUCE
- Public dataset - https://www.kaggle.com/ramjasmaurya/top-250s-in-imdb

### Setup
- Login to the GCP console using your Google account login
- Setup your account by completing the necessary formalities while login in for the first time
- Create a project with the requisite project-name 
- Complete the requisite billing details page (The deducted small amount would be recredited back with a few days, so don't worry :wink:)
- Select the sandwich button on the top-left corner and click BigQuery; you may pin the same as well for easier access in the future
- Select the project on the left-hand pane and create dataset (Similar to creating folders) or can use the public datasets
- You may create data-tables by uploading data 

### Loading data-tables to BigQuery
- Option 1 - One can upload relevant data-tables to the BigQuery dataset by using create-table option in the selected dataset and then using upload option
  - You may upload data-tables in CSV format
  - You may select the auto-detect option under Schema to automatically detect the data-type of the relevant columns
  - Then one may choose the advanced option to either append, overwrite or write if empty option
- Option 2 - Use Google cloud storage space and create bucket in the same region as that of the BigQuery dataset
  - Upload or drag/drop relevant files to the buckets in the GCP storage space
  - Use create data-table option and then select Google cloud storage to execute this mode of data upload

### Running/Saving/Scheduling queries
- For running queries on a particular datatable, you could select query option once you click on the button menu on the right hand side of the particular table
  - You can also select the particular datatable and then run query in new tab or split tab (the latter helps to give a simultaneous view on the code and datatable as well)
- Type in the requisite query and click RUN button once you see the green tick mark on the top right corner which is an indication of zero code error/s
- You may also format the query using format option which is visible under MORE menu
- You can select the query settings under MORE menu and set a destination table for the query results
- You can save the query using save query option under save menu
- You can schedule the query using create new shceduled query option under schedule menu
  - Type in the requisite date/time/weekday option for the schedule to run and the destination table as well
- One may access the scheduled queries on the left pane of the screen and the saved queries from the bottom pane

### SQL queries
#### Basic query
- Basic structure of the query would be as below:
```
SELECT <Column names>, <Define fucntion <Columns>>,
FROM <Table-name>
WHERE <Condition>
GROUP BY <Column-name> # Group the repeated/duplicate data entries of the particular column/s
ORDER BY <Column-name> # Sort the result using the data in the particular column; Default option is Ascending order
```
- An example query run on the imdb ratings dataset from Kaggle is show below:
```
# Find those movies whose rating is greater than or equal to 9 and sort with ratings in descending mode along with the respective year
SELECT movie_name_, Year, RATING,
FROM
  `crafty-sanctum-310406.practice_dataset.imdb_movie_ratings`
WHERE RATING >= 9
GROUP BY movie_name_, Year, RATING
ORDER BY RATING DESC 
```
