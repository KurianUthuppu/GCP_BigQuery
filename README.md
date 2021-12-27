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
