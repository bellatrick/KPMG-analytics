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

#### Customer demographic
1. The gender has inconsistency values where M/F and Male/Female are both being used.
2. DOB has 87 missing values and an inaccurate date with age of 180 years.
3. Job title has 506 missing values.
4. Job industry has 656 N/A values.
5. There is an invalid column called default with undecipherable values.

### Project goal
From a list of 1000 potential customers, use their demographics and attributes to analyse high value potential customers

### Identify relevant columns
Past 3-year Bike-related Purchases: Since this column represents the customer's purchasing activity, it can be an important indicator of profitability. Assign a weight of 0.4 to indicate its significance.

Wealth segment: This provides the demography of wealth the customer falls into in the economy and provides insights into their purchasing power. Assign a weight of 0.3 to indicate its significance.

Property Valuation: The value of the customer's property may be an indirect indicator of their purchasing power and potential profitability. Assign a weight of 0.2 to capture this factor.

Owns Car: This column suggests the customer's transportation situation, which can be relevant to their potential bike-related purchases. Assign a weight of 0.1 to account for its influence.

#### Other columns to get insights into demographic purchases
1. job_industry_category
2. Age
3. State

### Define the Calculation Logic
To estimate the customer's profitability value, the following calculation will be used:
Customer Profitability Value = (Weight1 * NormalizedValue1) + (Weight2 * NormalizedValue2) + (Weight3 * NormalizedValue3) + (Weight4 * NormalizedValue4)


