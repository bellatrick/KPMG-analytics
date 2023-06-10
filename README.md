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
Standard cost and list price columns will be used to calculate the profitability of a product and in turn will be used to determine customers that provide the highest value to Sprocket brand. Assign a weight of 0.3
Past 3-year Bike-related Purchases: Since this column represents the customer's purchasing activity, it can be an important indicator of profitability. Assign a weight of 0.2 to indicate its significance.

Wealth segment: This provides the demography of wealth the customer falls into in the economy and provides insights into their purchasing power. Assign a weight of 0.2 to indicate its significance.

Property Valuation: The value of the customer's property may be an indirect indicator of their purchasing power and potential profitability. Assign a weight of 0.2 to capture this factor.

Owns Car: This column suggests the customer's transportation situation, which can be relevant to their potential bike-related purchases. Assign a weight of 0.1 to account for its influence.

#### Other columns to get insights into demographic purchases
1. job_industry_category
2. Age
3. State

### Define the Calculation Logic
To estimate the customer's profitability value, the following calculation will be used:
Customer Profitability Value = (Weight1 * NormalizedValue1) + (Weight2 * NormalizedValue2) + (Weight3 * NormalizedValue3) + (Weight4 * NormalizedValue4)

After Normalizing the columns: The DAX formula below is used to calculate the profitability value for all the customers:

```dax
Customer Profitability = (0.2 * AVERAGE([Normalized past_3_years])) 
+ (0.3 * AVERAGE(Purchases[Normalized profitability]))
+ (0.2 * AVERAGE(CustomerAddress[Normalized valuation]))
+ (0.2 * AVERAGE(CustomerDemographic[Normalized Wealth Segment]) 
+ (0.1 * AVERAGE(CustomerDemographic[Normalize owns car]))
)
```
### Analysis
1. The top 1000 customers with the highest potential profitability provided more insights into the customers demographics.
![image](https://github.com/bellatrick/KPMG-analytics/assets/74540938/19a1ae41-2d98-4e4c-913e-8d60a2f53b66)
There seem to be no correlation at all between car ownership and Bicycle sales and Bicycles are bought more by middle aged people. This could be because Parents who already will often buy the bicycles for their kids.
![image](https://github.com/bellatrick/KPMG-analytics/assets/74540938/17191e9b-159a-42a9-868b-c9df999245e8)
![image](https://github.com/bellatrick/KPMG-analytics/assets/74540938/0a8a4a44-0c25-482d-8a33-40362466108c)
2. The most popular customer base by wealth segment is the masses with about 50.86 total sales and profitability coming from that demography.
![image](https://github.com/bellatrick/KPMG-analytics/assets/74540938/693e63d1-3d8a-4999-b867-3b261f7d6003)

4. New south Wales has a significantly higher proftability than other States, because the customer base from New South Wales seem to be higher than the other states.
![image](https://github.com/bellatrick/KPMG-analytics/assets/74540938/09d05a48-191e-47ee-805f-70dc8ee23d4f)
![image](https://github.com/bellatrick/KPMG-analytics/assets/74540938/89147eb2-06d1-4dd3-a7b9-8535dd12223c)

The full report can be found here with more insights and recommendations.
[Sprocket bi MAIN PDF.pdf](https://github.com/bellatrick/KPMG-analytics/files/11713256/Sprocket.bi.MAIN.PDF.pdf)




