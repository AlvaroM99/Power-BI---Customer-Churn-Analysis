# Power BI - End to End Customer Churn Analysis
</br>
<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/11e31663-fae6-49ff-947c-ead86214b4e5">
</p>

## Index

- [Overview](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#overview)
- [Dataset](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#dataset)
- [Guiding Questions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#guiding-questions)
- [Data Analysis](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#data-analysis)
- [Conclusions](https://github.com/AlvaroM99/Power-BI---Customer-Churn-Analysis#conclusions) 
</br>

## Overview

<p align="justify"> The process of churn analysis involves examining the frequency at which a company's customers stop using their services. By assessing the product and how it is used, businesses can minimize churn. High churn rates put pressure on a company to constantly acquire new customers, and even small increases in churn can be detrimental. Customer churn data analysis provides valuable insights for making informed decisions and developing strategies to prevent further churn. </p>

</br>

## Dataset

<p align="justify"> The data obtained from a bank is in the form of a .csv file. Upon initial inspection, the data appears to be relatively free of errors and inconsistencies. Therefore, the process of data wrangling will primarily involve preparing and transforming the data, rather than cleaning it. The dimensions of the .csv file are 10,000 rows and 12 columns, one of which is labeled as churn. The remaining 11 columns correspond to different factors that may impact the churn rate, and will be listed below:
These are the different pieces of information that the bank collects about its clients: </p>

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

<p align="justify"> The aim of this analysis is to create visual representations of important key performance indicators (KPIs) using data from a bank. In addition to sorting and organizing this data, the focus will be on examining churned customers and the churn rate. These will serve as the dependent variable in most of the visualizations. By comparing multiple factors against the attrition rate (churn rate), we can identify relationships and patterns that will be useful in making decisions and deploying strategies. </p>

- What variables have the biggest impact on Churn Rate?
- How do they affect our key parameter and each other?
- Based on the indicators, what strategies can we use to decrease customer loss?
  
</br>

## Data Analysis

### Establishing the Data Pathway after downloading the files

<p align="justify"> If you want to share a Power BI dashboard with others, the best way is to upload it to Power BI Services. However, I'm not able to do so due to restrictions on my Microsoft 365 account. Instead, I've uploaded the file in .pbix format. To access the data transformation through Power Query Editor, you'll need to establish the pathway for Power BI to connect to the data source, which is the uploaded csv file. Save the location of the raw data wherever you store it. First, click on "Transform data", which will open Power Query Editor. If the csv file is not found in the established route of the .pbix file, an error will appear. From there, go to "Data source settings", select Change source, and paste the csv file location. After doing this, click "Refresh preview" to view all the data, transformations, and preparations. In Power BI Desktop, apply the changes and none of the KPIs or plots should be altered. </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/a16e44ef-1118-41ce-ada0-5a5df99e4613">
</p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/45d57f4e-c68a-4d73-9474-f0d443d04807">
</p>

</br>

### 1. Data Connection

<p align="justify"> To begin creating a Power BI model, the first step is to connect to the data source. You can do this by going to "Get data" and selecting "Text/CSV." Once you have selected the csv file, a preview of the data table will be displayed. To ensure that the data is clean and properly formatted for analysis, click on "Transform" and Power Query Editor will open. If the data were completely clean and reshaped in the way we need it, you could directly load it into the model, but that is not the case here since we have raw data. </p>

</br>

### 2. Data Wrangling (Cleaning, Formatting & Reshaping)

<p align="justify"> When analyzing data with Power BI, the Power Query Editor is a useful tool that can make the data preparation process less tedious. To keep track of any alterations made to the data, it's essential to observe the **"Applied Steps"** window located on the editor's right side. Additionally, an M code command will be generated in the top **formula bar**. Another noteworthy feature is the **"Queries"** window on the left side, where we can obtain data from the main data frame to create smaller tables and continue with the Data Modelling process later on. Although headers' promotion and data type changes are usually automatic, the default changes can be removed from the "Applied Steps" window and manually adjusted in the home tab. After preparing the data, it's crucial to search for any irrelevant information to reduce the dataset as much as possible without missing crucial variables. This is a good habit for any data analyst. </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/bfa63408-d889-4aa6-b960-fe4e902dfbd0">
</p>

</br>

<p align="justify"> I will be removing the "estimated_salary" column as it is a prediction and we already have the more tangible "balance" column. After that, I will rename all the columns to make them more descriptive for both data transformations and analysis, as well as for users who view the visualizations. The final step in the preliminary reshaping process will be to change the data types. By default, they are set to text type (csv file), but sometimes we will need to change it to whole number type, fixed decimal number, or leave it as text type. This can be done by clicking on the left side of each column header. </p>

<p align="justify"> I can help make the "products" column easier to understand by changing its values of [1, 2, 3, 4] to [prod 1, prod 2, prod 3, prod 4]. To do this, we can select the "products" column and click on "Column from examples" in the "Add Column" tab. This will create a new column where we can input "Prod 1" and Power BI will automatically change the 1 value to "Prod 1". This prefix change will be applied to all values while maintaining their previous number. Once we confirm that the values are correctly reshaped, we can give the column a header and remove the previous "products" column. </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/20fcbf11-7572-44b0-ae30-9199b0b871c4">
</p>

</br>

<p align="justify"> In order to improve readability, I will be replacing the binary values in the "Credit card", "Active member", and "Churn" columns with text values. To do this, I will change the data type of the columns from "whole number" to "text". Then, by right-clicking the header and selecting "replace values", I can easily make the changes. This technique works best when there are only a few different values in the same column. When the dialog window appears, I simply need to input the value to find and the value to replace it with. </p>

  - For the "Credit card" column I renamed it to "Credit Card Status" and replaced the values as follows: [0-Not Owned, 1-Owned]
  - For the "Active member" column I renamed it to "Activity Status" and replaced the values as follows: [0-Inactive, 1-Active]
  - For the "Churn" column I renamed it to "Churn Status" and replaces the values as follows: [0-Not Churned, 1-Churned]

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/44f48484-5bff-4cee-8e10-7dd90912a82d">
</p>

</br>

<p align="justify"> When looking at churn rate, it might be interesting to analyze the variables of "Age", "Credit Score", and "Account Balance". To do this, we can go to the "View" tab and select "Column profile". This will show us a chart of the column distribution and important parameters in descriptive statistics such as null values, min, max, average, std, and more on the left side. </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/a1379299-d3ae-4cd4-a15b-8f6653f1eef0">
</p>

<p align="justify"> After completing the previous task, we can determine the number of unique values and their distribution. If there are numerous distinct values, it can be helpful and meaningful to classify the data in those variables of interest into groups or categories such as <20, 20-30, 30-40, etc. To achieve this, we need to select our column of interest and click on "Conditional column" in the "Add column" tab. This will launch the "Add Conditional Column" dialog window where we must specify the new column name, the data source column name, the operator, value, and output for each category we want to generate. We should repeat this process for every category we intend to create using a new clause each time. We will create a conditional column for "Age" called "Age Groups", another for "Credit Score" named "Credit Score Groups" and another one for "Account Balance" called "Account Balance Groups". </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/a5ce365b-0dfc-4ff2-b9bc-a38cc09307fe">
</p>

</br>

### 3. Data Modeling

<p align="justify"> After cleaning and preparing our data, we need to create separate charts for each new conditional column added. This is because we cannot sort the values correctly when the data type is text. For instance, categories with "<" symbol should appear first but are relegated to the end since numbers are interpreted before symbols in text data types. To solve this problem, we need to create new tables for these categorized variables, which will later be visualized with the churn rate. Then we can add a column in these new charts, which will allow us to rearrange the categories created for each variable of interest. </p>

<p align="justify"> In order to create charts, we can utilize the "Queries" window. First, we should right-click on the chart we already have and select "Reference". This will result in a new chart with the same dimensions, data, and applied steps as the original. We can then rename it in the "Properties" window above the "Applied Steps" window. Next, we want to only leave the column labeled "Age Groups" and its unique values. To achieve this, navigate to the "Home" tab and choose the "Age Groups" column. Right-click on it and select "Remove other columns". Finally, while keeping the column selected, go to the "Remove Rows" option in the same tab and select "Remove Duplicates". </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/20cd0b86-6425-4425-ade2-dfc04cebd6e0">
</p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/201b9c69-d327-4ff3-a224-4455ba211c9b">
</p>

</br>

<p align="justify"> We now have the chart with its unique values, but we still need to sort them by creating an index column. One option is to use the "Index column" button (From 1) in the "Add Column" tab. However, we still face an issue because the data type is text. To solve this, I will use the "Conditional Column" technique again. When the dialog window opens, we need to set the same parameters as before. This time, the operator will be "equal," and the range from the "Age Groups" column will be linked to an ID number that corresponds with the "Age Groups" categories' order. The same steps will be applied to the "Account Balance Groups" and "Credit Score Groups" columns. </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/b1316017-3336-4a64-9ca0-dccaa6daf210">
</p>

</br>

<p align="justify"> After completing the data preparation and modeling, we need to click on the "Close & Apply" button. This will close the Power Query Editor and apply all the transformations to the dataset. The updated dataset will be uploaded to the Power BI model in the Power BI Desktop window. However, we still need to review the data relationships of the data model. To do this, we need to go to the "Model View" tab on the right side of the workspace in Power BI Desktop. Here, we can edit and view the relationships between charts. Power BI has already set the "... Groups" charts as lookup tables, which reference the main table "Customer Data" in some of their columns. </p>

<p align="center" width="100%">
    <img width="65%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/fe2391cc-b95b-430c-928a-6355e691d9ce">
</p>

</br>

### 4. Creating new measures with DAX

<p align="justify"> In order to build some of the graphs new measures needs to be added into the "Customer Data" chart, to build those formulas we will be using DAX. DAX is a collection of functions, operators, and constants also present in Excel that can be used in a formula or expression to calculate and return one or more values, in this case new measures (variables). A new calculation is created by right-clicking on the "Customer Data" chart and pressing "New measure". The calculations we are going to add are: Number of customers (Σ), Customers Lost, and Churn Rate. The DAX formulas for each calculation are the following:</p>

- Number of Customers = COUNT('Transformed Costumer Data'[Customer ID])
  
- <p align="justify"> Customers Lost = CALCULATE(COUNT('Transformed Costumer Data'[Churn Status]),'Transformed Costumer Data'[Churn Status] = "Churned"). // The CALCULATE( ) function allows us to execute another function, COUNT( ), if a given condition is fulfilled, the customer being labeled as "Churned" in the "Churn Status" column.</p>

- Churn Rate = [Customers Lost] / [Customers]

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/7c54b4cf-3768-462b-9991-ad97dfc182f0">
</p>

</br>


### 5. Data Visualization & Dashboard Customization



### 6. Save & Publish Report to Power BI Service


## Conclusions














## DOCUMENTATION IN PROGRESS
