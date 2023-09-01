# Power BI - End to End Customer Churn Analysis

## Index

- [Overview](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#overview)
- [Dataset](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#dataset)
- [Guiding Questions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#guiding-questions)
- [Data Analysis](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#data-analysis)
- [Conclusions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#conclusions) 

## Overview

Churn analysis is the evaluation of a company’s customer loss rate in order to reduce it. Churn can be minimized by assessing your product and how people use it. A high churn rate forces a business to compete with the stress of bringing new customers and even slight increases in it can be harmful. As such, a customer churn data analysis can provide useful insights to make informed decisions and develop future strategies to keep the churn rate at bay.

## Dataset

The data obtained from a bank is in the form of a .csv file. Upon initial inspection, the data appears to be relatively free of errors and inconsistencies. Therefore, the process of data wrangling will primarily involve preparing and transforming the data, rather than cleaning it. The dimensions of the .csv file are 10,000 rows and 12 columns, one of which is labeled as churn. The remaining 11 columns correspond to different factors that may impact the churn rate, and will be listed below:
- customer_id: The id of the bank clients
- credit_score: Score obtained by the customer over the years by using and purchasing services and products from the bank
- gender
- age
- tenure: How long have they been customers of the bank
- balance: Stands for the account balance of each client
- product_number: Which particular product are they contracting
- credit_card: Whether they had a credit card or not (binary) 
- active_member: Whether they were active clients or not (binary)
- estimated_salary: Estimated annual salary
- churn: Whether they are still clients or not (binary)


## Guiding Questions


## Data Analysis

### Establishing Data Pathway for Data Connection

Ideally the Power BI dashboard should be uploaded to Power BI Services in order to publish it and for others to consult it. However, my Microsoft 365 account doesn't allow it. Therefore the file is completely uploaded under the .pbix format. The first thing to do if someone wants to consult the data transformation through Power Query Editor is to establish the pathway that Power BI will use to connect to the data source (the csv file uploaded alongside). Wherever the csv file is stored, please copy the location and paste it after clicking Transform Data (Power Query Editor opens up) > Data Source Setting > Change source. Once done click on Refresh Preview and all data with its transformations and preparations must be returned. In Power BI Desktop apply the changes and none of the KPIs ore plots should change.

### 1. Data Connection

### 2. Data Wrangling (Cleaning, Formatting & Reshaping)

### 3. Data Modeling

### 4. Creating new measures with DAX

### 5. Data Visualization & Dashboard Customization

### 6. Save & Publish Report to Power BI Service


## Conclusions














## DOCUMENTATION IN PROGRESS
