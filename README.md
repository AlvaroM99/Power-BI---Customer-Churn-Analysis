# Power BI - End to End Customer Churn Analysis

## Index

- [Overview](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#overview)
- [Dataset](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#dataset)
- [Guiding Questions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#guiding-questions)
- [Data Analysis](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#data-analysis)
- [Conclusions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#conclusions) 

## Overview

The process of churn analysis involves examining the frequency at which a company's customers stop using their services. By assessing the product and how it is used, businesses can minimize churn. High churn rates put pressure on a company to constantly acquire new customers, and even small increases in churn can be detrimental. Customer churn data analysis provides valuable insights for making informed decisions and developing strategies to prevent further churn.

## Dataset

The data obtained from a bank is in the form of a .csv file. Upon initial inspection, the data appears to be relatively free of errors and inconsistencies. Therefore, the process of data wrangling will primarily involve preparing and transforming the data, rather than cleaning it. The dimensions of the .csv file are 10,000 rows and 12 columns, one of which is labeled as churn. The remaining 11 columns correspond to different factors that may impact the churn rate, and will be listed below:
These are the different pieces of information that the bank collects about its clients:

- Customer ID: This is a unique identifier given to each bank client.
- Credit Score: This is a score that the bank gives to each client based on their history of using and purchasing the bank's services and products over time.
- Gender: This is the gender of the client.
- Age: This is the age of the client.
- Tenure: This is how long the client has been a customer of the bank.
- Balance: This is the current account balance of the client.
- Product Number: This is the specific product that the client has contracted with the bank.
- Credit Card: This is a binary value indicating whether the client has a credit card with the bank or not.
- Active Member: This is a binary value indicating whether the client is an active member of the bank or not.
- Estimated Salary: This is an estimated annual salary for the client.
- Churn: This is a binary value indicating whether the client is still a client of the bank or not.


## Guiding Questions

The aim of this analysis is to create visual representations of important key performance indicators (KPIs) using data from a bank. In addition to sorting and organizing this data, the focus will be on examining churned customers and the churn rate. These will serve as the dependent variable in most of the visualizations. By comparing multiple factors against the attrition rate (churn rate), we can identify relationships and patterns that will be useful in making decisions and deploying strategies.

## Data Analysis

### Establishing Data Pathway for Data Connection

If you want to share a Power BI dashboard with others, the best way is to upload it to Power BI Services. However, I'm not able to upload it due to restrictions on my Microsoft 365 account. Instead, I've uploaded the file in .pbix format. To access the data transformation through Power Query Editor, you'll need to establish the pathway for Power BI to connect to the data source, which is the uploaded csv file. Save the location of the raw data wherever you store it. First, click on Transform data, which will open Power Query Editor. If the csv file is not found in the established route of the .pbix file, an error will appear. From there, go to Data source settings and select Change source. After doing this, click Refresh preview to view all the data, transformations, and preparations. In Power BI Desktop, apply the changes and none of the KPIs or plots should be altered.

![image](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/a16e44ef-1118-41ce-ada0-5a5df99e4613)


![image](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/45d57f4e-c68a-4d73-9474-f0d443d04807)


### 1. Data Connection

### 2. Data Wrangling (Cleaning, Formatting & Reshaping)

### 3. Data Modeling

### 4. Creating new measures with DAX

### 5. Data Visualization & Dashboard Customization

### 6. Save & Publish Report to Power BI Service


## Conclusions














## DOCUMENTATION IN PROGRESS
