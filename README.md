# KPMG-analytics
Sprocket Central Pty Ltd , a medium size bikes & cycling accessories organization, has approached Tony Smith (Partner) in KPMG’s Lighthouse & Innovation Team. Sprocket Central Pty Ltd  is keen to learn more about KPMG’s expertise in its Analytics, Information & Modelling team. 

The client provided KPMG with 3 datasets:

Customer Demographic 
Customer Addresses
Transactions data in the past 3 months

## Step 1: Data Assessment and cleaning

Before starting anything, the data quality needs to be thoroughly checked and any necessary data cleaning process will be done. I will be using a standard data quality framework to check for the following:

1. Completeness
2. Consistency
3. Accuracy
4. Currency
5. Uniqueness
6. Validity
7. Relevancy

### My findings:

#### Transaction Table
1. Online order column has 360 missing values
2. The brand and product line, class and size columns has 197 missing values.
3. Standard cost column has 3 values that are not formatted correctly.
4. The product_first_sold_date column is formatted as a number.

#### New customers table
1. Job title has 106 missing cells.
2. Job industry has 167 N/A values.

#### Cutomer demographic
1. The gender has inconsistency values where M/F and Male/Female are both being used.
2. DOB has 87 missing values and an inaccurate date with age of 180 years.
3. Job title has 506 missing values.
4. Job industry has 656 N/A values.
5. There is an invalid column called default with undecipherable values.
