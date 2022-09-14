# Ex-01_DS_Data_Cleansing
# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Get the information about the data

## STEP 3
Remove the null values from the data

## STEP 4
Save the Clean data to the file

# CODE

import pandas as pd
import numpy as np
import seaborn as sns

df1 = pd.read_csv("Data_set.csv")
df1

df1.head()

df1.describe()

df1.info()

df1.tail()

df1.shape

df1.columns

df1.isnull().sum()

df1.duplicated()

#Using mode method to fill the data in columns as Object(String)
#mode()[0] - Takes the most reccuring value and fills the empty cells
df1['show_name'] = df1['show_name'].fillna(df1['show_name'].mode()[0])
df1['aired_on'] = df1['aired_on'].fillna(df1['aired_on'].mode()[0])
df1['original_network'] = df1['original_network'].fillna(df1['original_network'].mode()[0])

sns.boxplot(x="rating",data=df1)

#Using mean method to fill the data
df1['rating'] = df1['rating'].fillna(df1['rating'].mean())
df1['current_overall_rank'] = df1['current_overall_rank'].fillna(df1['current_overall_rank'].mean())
df1['watchers'] = df1['watchers'].fillna(df1['watchers'].mean())

#Checking the total no.of null values again
df1.isnull().sum()

#Checking info of the dataset to check all the columns have entries
df1.info()

# OUPUT

DATASET

![image](https://user-images.githubusercontent.com/94911373/190093436-90ce2dd8-b716-447b-9f60-71c5b49b15e1.png)



HEAD

![image](https://user-images.githubusercontent.com/94911373/190093548-9cea2d46-8eed-4b2f-a632-01c33334a71e.png)



DESCRIBE


![image](https://user-images.githubusercontent.com/94911373/190093661-0a93223a-3163-46d9-b214-9b5c0d4634de.png)



INFO

![image](https://user-images.githubusercontent.com/94911373/190093764-08db755d-b857-491d-a08a-63e9afb3a5b3.png)



TAIL


![image](https://user-images.githubusercontent.com/94911373/190093889-03f09456-685d-4c35-8a90-41e65782b9c3.png)



SHAPE

![image](https://user-images.githubusercontent.com/94911373/190093982-783753dc-2beb-4e5b-837c-893b427966c7.png)


isnull().sum() - Pre Cleaning


![image](https://user-images.githubusercontent.com/94911373/190094333-2063c657-97e2-45ec-9e41-dfd1cd842005.png)


DUPLICATES

![image](https://user-images.githubusercontent.com/94911373/190094425-5691ac99-eea5-4e5c-b0ef-1535542de8ca.png)


SNS PLOT-RATING



![image](https://user-images.githubusercontent.com/94911373/190095258-579be0ad-b99d-4159-a5ce-20336b123363.png)



isnull().sum() - Post Cleaning


![image](https://user-images.githubusercontent.com/94911373/190095341-2dcde588-859b-4a4c-823b-fec18dc059ee.png)



Info - Post Cleaning

![image](https://user-images.githubusercontent.com/94911373/190095444-26b55e49-de54-4dde-9285-325eaabcac36.png)


Result:

The given data is read and data cleaning is performed and the cleaned data is saved to a file.



