# Wrangling Process Report

The purpose of this report is to document the wrangling efforts made in WeRateDog twitter data analysis. Here, the wrangling efforts made will be described briefly for an overview. 

In the analysis made, data wrangling is divided into 3 main parts:
- Gathering
- Assessing 
- Cleaning

Each section would be spoken about breifly:


## Section 1: Gathering

For this project three datasets were gotten from different sources and each tested one's ability to gather data from different sources, how to handle and import different these different datasets into jupyter notebook. 
* The first file was twitter_archive_enhanced.csv
- This file was given to stdents by Udacity which is one of the common source of data gathering (file at hand). The file, twitter_archive_enhanced.csv, was a typical csv file and it was read into pandas DataFrame. 
- The second file was downloaded programmatically from the internet. The file, image-prediction, contained the result of a  machine learning dog classification. It determines whether the picture uploaded is a dog or not.
- The third file was gotten from twitter api, a different source of gathering data. Its a json file and it was read into the pandas DataFrame. 


In a nutshell, the gathering process tested my data gathering skills as different files were downloded from 3 sources;
- Source at hand
- Programmatically downloading files from the internet and 
- Getting data through twitter api.
<br> This has solidified my knowledge on data gathering.

# Section 2: Assessing 

In this section, efforts were made to understand the dataset at hand. After understanding each dataset, its degree of data quality and tidiness was looked into. This was done both visually and programmatically using pandas library. Functions such as info(), value_counts(), sample(), head() were used among others. 

<br> Upon assessing each dataframe's data quality and tidiness issues, a summary was derived for an easier data cleaning workflow.


> ## Data Quality and Tidiness Summary

>> ### Data Quality Issues
   <br> i.`twt_arc` table: Timestamp column's +0000 is not needed.
   <br> ii. `twt_arc` table: Timestamp column is object instead of datetime data type
   <br> iii. `twt_arc` table: Source column is ambiguous.
   <br> iv. `twt_arc` table: Some tweet_id are retweets.
   <br> v. `twt_arc` table: Columns like in_reply_to_status_id, in_reply_to_user_id,retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp and expanded_urls are not needed.
   <br> vi.  `twt_arc` table: There are 745 'none' and 55 'a' values in the name column
   <br> vii. `twt_arc` table: There are a lot of wrong names in name column, most of the wrong names are in lowercase as well.
   <br> viii. `twt_arc`table: Names are in uppercase instead of lowercase.
   <br> ix. `twt_arc` table: There are lots of none values in types of dog stages columns.
   <br> x    `all` table: The datatype for the tweet_id variable is in int.
   <br> xi. `img_pred` table: Some values in the p1_dog are not classified as dogs.
   <br> xii. `img_pred` table: Unneeded columns in img_pred table.

>> #### Tidiness issue 
   <br> i. `twt_arc` table: doggo,floofer,pupper,puppo has multiple columns.
   <br> ii.`img_pred` table: As a seperate table this data offers little value to the project analysis.
   <br> iii. `twt_api` table: As a seperate table this data offers little value to the project analysis. 


 



# Section 3: Data Cleaning

In this section an attempt to rectified the aforementioned issues in the data assessing section was carried out. 
<br> Using the `Define`,`Code` and `Test` method for a more structured presentation. 
- Define:</b> It described the actions that were done to tackle a stated issue.
- Code:</b> The action written in code. This is where the actual cleaning was done.
- Test:</b> To verify if the result gotten was correct.

The most tidious of all sections was the data assessing an cleaning section because it was a repetitive process. 
<br> Issues might arise while cleaning and one will have to revisit the assessing stage to correct or add more data quality or tidiness issue. 

<br> One of the issues faced in data cleaning process was replacing none values with actual dog names from the text column `data quality issue v & vi` and while trying to merge the dataframe as one using different columns to merge `data tidiness issue ii & iii`  
<br> To tackle the missing names, some were rectified while others were not. It was an tidious process of data cleaning but it paid off as it improved the data quality of the analysis.
<br> The merging issue was rectified by changing `twt_api.id` column name to `twt_api.tweet_id`. Ths brought uniformity into the dataframe and it was merged easily by that simple column name change.

To tackle these issues a lot of python principles were revisited and a lot of research was done.  
