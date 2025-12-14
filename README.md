# DS-2002 Final Capstone Project 
Restaurant Date Lakehouse (Local Implementation)

## Project Overview
For this project I did a complete data lakehouse structure designed to be like a single restaurants POS system (inspo from Square as i have had to work with the POS system a lot for work). Goal here is to analyze historical and fake real-time transactions in order to understand what was sold and when by whom. 

Used Apache Spark, Delta Lake, and Structured Streaming following the bronze to silver to gold design patter from class labs. 

## Arc Summary:

Data sources (3 req)
- MySQL (Relational/SQL)
    - Customers
    - Date Dimension
- MongoDM Atlas (NoSQL)
    - Menu Items 
- Local CSV Files (File based source)
    - Employees
    - Order Types
- Streaming JSON FIles (local file stream)
    - order events nested line items - this simulating real time POS transactions


## Lakehouse Designs
- Bronze Layer
    - stored as delta tables
    - streaming JSON  using spark
- Silver Layer (Fact table)
    - order line fact records
    - integrated w all dim tables
- Gold Layer
    - aggregated queries that support the analysis

## Date Dim 
- This was created using the SQL script from class and populated into MySQL. 

## Other
- this was deployed entirely locally
- AZURE WAS NOT USED - as notified was allowed from TA
- spark runs locally using delta lake
