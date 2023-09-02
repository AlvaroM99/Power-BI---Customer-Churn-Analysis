# Power BI - End to End Customer Churn Analysis
</br>

## Index

- [Overview](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#overview)
- [Dataset](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#dataset)
- [Guiding Questions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#guiding-questions)
- [Data Analysis](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#data-analysis)
- [Conclusions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#conclusions) 
</br>

## Overview

The process of churn analysis involves examining the frequency at which a company's customers stop using their services. By assessing the product and how it is used, businesses can minimize churn. High churn rates put pressure on a company to constantly acquire new customers, and even small increases in churn can be detrimental. Customer churn data analysis provides valuable insights for making informed decisions and developing strategies to prevent further churn.

</br>

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
</br>

## Guiding Questions

The aim of this analysis is to create visual representations of important key performance indicators (KPIs) using data from a bank. In addition to sorting and organizing this data, the focus will be on examining churned customers and the churn rate. These will serve as the dependent variable in most of the visualizations. By comparing multiple factors against the attrition rate (churn rate), we can identify relationships and patterns that will be useful in making decisions and deploying strategies.

- What variables have the biggest impact on Churn Rate?
- How do they affect our key parameter and each other?
- Based on the indicators, what strategies can we use to decrease customer loss?
</br>

## Data Analysis

### Establishing the Data Pathway after downloading the files

If you want to share a Power BI dashboard with others, the best way is to upload it to Power BI Services. However, I'm not able to do so due to restrictions on my Microsoft 365 account. Instead, I've uploaded the file in .pbix format. To access the data transformation through Power Query Editor, you'll need to establish the pathway for Power BI to connect to the data source, which is the uploaded csv file. Save the location of the raw data wherever you store it. First, click on "Transform data", which will open Power Query Editor. If the csv file is not found in the established route of the .pbix file, an error will appear. From there, go to "Data source settings", select Change source, and paste the csv file location. After doing this, click "Refresh preview" to view all the data, transformations, and preparations. In Power BI Desktop, apply the changes and none of the KPIs or plots should be altered.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/a16e44ef-1118-41ce-ada0-5a5df99e4613">
</p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/45d57f4e-c68a-4d73-9474-f0d443d04807">
</p>

</br>

### 1. Data Connection

To begin creating a Power BI model, the first step is to connect to the data source. You can do this by going to "Get data" and selecting "Text/CSV." Once you have selected the csv file, a preview of the data table will be displayed. To ensure that the data is clean and properly formatted for analysis, click on "Transform" and Power Query Editor will open. If the data were completely clean and reshaped in the way we need it, you could directly load it into the model, but that is not the case here since we have raw data.

</br>

### 2. Data Wrangling (Cleaning, Formatting & Reshaping)

When analyzing data with Power BI, the Power Query Editor is a useful tool that can make the data preparation process less tedious. To keep track of any alterations made to the data, it's essential to observe the **"Applied Steps"** window located on the editor's right side. Additionally, an M code command will be generated in the top **formula bar**. Another noteworthy feature is the **"Queries"** window on the left side, where we can obtain data from the main data frame to create smaller tables and continue with the Data Modelling process later on. Although headers' promotion and data type changes are usually automatic, the default changes can be removed from the "Applied Steps" window and manually adjusted in the home tab. After preparing the data, it's crucial to search for any irrelevant information to reduce the dataset as much as possible without missing crucial variables. This is a good habit for any data analyst.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/bfa63408-d889-4aa6-b960-fe4e902dfbd0">
</p>

</br>

I will be removing the "estimated_salary" column as it is a prediction and we already have the more tangible "balance" column. After that, I will rename all the columns to make them more descriptive for both data transformations and analysis, as well as for users who view the visualizations. The final step in the preliminary reshaping process will be to change the data types. By default, they are set to text type (csv file), but sometimes we will need to change it to whole number type, fixed decimal number, or leave it as text type. This can be done by clicking on the left side of each column header.

Then I will reshape the "products" column by changing its [1, 2, 3, 4] values by [prod 1, prod 2, prod 3, prod 4], so that it is easier to understand that those four different values are referring to four different products. There are several options to do so, already with the ¨products¨ column selected let's click on "Colum from examples" in the "Add Column" tab. This will add a new column where we can type in "Prod 1" and Power BI will automatically change the 1 value by "Prod 1"; this change of adding the prefix "Prod" will be applied to every single value maintaining the previous number. Once we reviewed that the values are properly reshaped we can give the column a header and get rid of the previous "products" column.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/20fcbf11-7572-44b0-ae30-9199b0b871c4">
</p>

</br>

Following with the binary values columns, that is "Credit card", "Active member" and " Churn"; I will be replacing the binary values with text values for each column. Again the purpose beneath these changes is legibility. In this case changes can be made by altering the data type of the columns from "whole number" to "text", then we right click the header and go to replace values. It is better to do this technique when we have few different values in the same column. When the dialog window opens we only have to give de value to find and the value to replace it.

  - For the "Credit card" column I renamed it to "Credit Card Status" and replaced the values as follows: [0-Not Owned, 1-Owned]
  - For the "Active member" column I renamed it to "Activity Status" and replaced the values as follows: [0-Inactive, 1-Active]
  - For the "Churn" column I renamed it to "Churn Status" and replaces the values as follows: [0-Not Churned, 1-Churned]

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/44f48484-5bff-4cee-8e10-7dd90912a82d">
</p>

</br>

So the variables we are interested in analyzing when confronted with the churn rate are "Age", "Credit Score" and "Account Balance". First, we will be heading to the "View" tab where we can click on "Column profile". This will display a simple chart of the column distribution and an overview on the left side of the most important parameters in descriptive statistics, such as the presence of null values, min, max, average, std, and more. Once this is done we can see how many distinct values there are and how do they distribute. When there are a lot of distinct values it's useful and meaningful to categorize the data into some sort of groups or categories, for example: <20, 20-30, 30-40, and so on. To do so we click on "Conditional column" in the "Add column" tab while we have our column of interest selected, this will open the "Add Conditional Column" dialog window where we must set the new column name, the column name from where we are retrieving the data, the operator, value and output. This has to be done for each category or group we want to create and will do so by adding a new clause at the bottom of the opening clause.

### 3. Data Modeling

### 4. Creating new measures with DAX

### 5. Data Visualization & Dashboard Customization

### 6. Save & Publish Report to Power BI Service


## Conclusions














## DOCUMENTATION IN PROGRESS
