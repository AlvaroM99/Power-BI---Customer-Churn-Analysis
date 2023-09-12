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
  - [Establishing the Data Pathway after downloading the files](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#establishing-the-data-pathway-after-downloading-the-files)
  - [Data Connection](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#1-data-connection)
  - [Data Wrangling (Cleaning, Formatting & Reshaping)](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#2-data-wrangling-cleaning-formatting--reshaping)
  - [Data Modeling](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#3-data-modeling)
  - [Creating new measures with DAX](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#4-creating-new-measures-with-dax)
  - [Data Visualization & Dashboard Customization](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#5-data-visualization--dashboard-customization)
  - [Save & Publish Report to Power BI Service](https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis#6-save--publish-report-to-power-bi-service)
    
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

<p align="justify"> When analyzing data with Power BI, the Power Query Editor is a useful tool that can make the data preparation process less tedious. To keep track of any alterations made to the data, it's essential to observe the "Applied Steps" window located on the editor's right side. Additionally, an M code command will be generated in the top formula bar. Another noteworthy feature is the "Queries" window on the left side, where we can obtain data from the main data frame to create smaller tables and continue with the Data Modelling process later on. Although headers' promotion and data type changes are usually automatic, the default changes can be removed from the "Applied Steps" window and manually adjusted in the home tab. After preparing the data, it's crucial to search for any irrelevant information to reduce the dataset as much as possible without missing crucial variables. This is a good habit for any data analyst. </p>

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

<p align="justify"> To create certain graphs, new measures must be added to the "Customer Data" chart using DAX. DAX is a set of functions, operators, and constants found in Excel that can be utilized to calculate and return new measures (variables). To create a new calculation, right-click on the "Customer Data" chart and select "New measure". The three calculations that will be added are: Number of customers (Σ), Customers Lost, and Churn Rate. The DAX formulas for each calculation are as follows:</p>

- Number of Customers = COUNT('Transformed Costumer Data'[Customer ID])
  
- <p align="justify"> Customers Lost = CALCULATE(COUNT('Transformed Costumer Data'[Churn Status]),'Transformed Costumer Data'[Churn Status] = "Churned"). // The CALCULATE( ) function allows us to execute another function, COUNT( ), if a given condition is fulfilled, the customer labeled as "Churned" in the "Churn Status" column.</p>

- Churn Rate = [Customers Lost] / [Customers]

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/7c54b4cf-3768-462b-9991-ad97dfc182f0">
</p>

</br>


### 5. Data Visualization & Dashboard Customization

<p align="justify"> Power BI is a strong contender in the data visualization market, despite Tableau's recent rise in popularity. While Tableau offers easier graph creation and visually appealing dashboards, Power BI can still create powerful and visually appealing dashboards with a little more effort. One of Power BI's main advantages is its powerful Power Query Editor, which allows users to work on all data analysis steps within one program.</p>

I will implement 4 types of charts:

- Card chart: It works as a KPI.

- Donut chart: It's a powerful plot to see distributions.

- <p align="justify"> Line and clustered column chart: It's the best way of representing the distribution of various parameters, thus gaining insights of its relationships.</p>

- <p align="justify"> Gauge chart: It can be used in multiple situations, in our case it will act as a graphic representation of the actual churn rate against the target churn rate.</p>

</br>

<p align="justify"> Let's begin by creating simple card graphs to display dynamic data such as "Number of Customers" and "Churn Rate". These graphs act as KPIs and do not show distribution or relationships between variables. Next, we will insert 5 donut charts to gain insights into data distribution based on gender, location, activity status, credit card status, and purchased products. These graphs are more complex and require selecting "Number of Customers" as the value and selecting the relevant parameter's distribution as the legend, for example, gender. To achieve this, select the donut chart, drag the variables or measures from the "Data" tab on the right into the "Values" or "Legend" field located in the "Add data to your visual" tab within the "Visualizations" tab next to the "Data" tab.</p>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/6a86b3df-9324-4144-beb6-5f0d72ac32ac">
</p>

</br>

<p align="justify"> To customize a chart, select it and go to the "Visualization" tab. Then, click on "Format your visual" located next to "Add data to your visual". This will bring up two new tabs, "Visual" and "General", where you can adjust all aspects of the chart including effects, properties, legend, title, slices, ticks, and labels. Additionally, the general dashboard can be customized through the "View" tab.</p>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/af66d8d4-a602-49db-9d0a-ce7767ac4b8e">
</p>

</br>

<p align="justify"> Let's take a look at how to create the most complex chart in this dashboard - the line and clustered column chart. It's ideal for displaying the distribution of customers by age groups and their corresponding churn rate. To get started, I begin by creating an empty chart and adding data to it. I drag the "Age Groups" from the "Age Groups" table to the "X-axis" field and choose not to use the "Customer Data" table so that I can easily sort the groups in the chart. Next, I drag the "Number of Customers" measure to the "Column y-axis" field and repeat the same for the "Churn Rate" measure in the "Line y-axis" field. However, the generated chart is unsorted when it comes to age groups. To remedy this, I select the "Age Groups" column in the "Age Groups" table within the "Data" tab. After highlighting both the column and the chart, I go to the "Column Tools" tab, click on "Sort by column," and choose "Age Groups ID." This action sorts the age groups in the table but not the chart. To sort the chart, I go to the top-right of the chart, click on "more options," select "sort axis," and choose "Age groups & Sort ascending." These same steps must be taken to plot the customer and churn rate distributions by "Account Balance Groups" and "Credit Score Groups."</p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/15c5d93f-569b-42a5-81b3-517ca169ba4a">
</p>

</br>

<p align="justify"> Let's take a look at how to construct the last plot, the gauge chart. To create this graph, we need to have the actual churn rate value, maximum and minimum values, and the target value. However, the last three values are not available in the "Transformed Customer Data" table, so we need to add them. To do this, we will go back to the Power Query Editor and select "Custom Column" under the "Add column" tab. For each of the three columns, we will set the header name, the value, and the data type (percentage). The minimum value will be set at 0, the maximum at 1, and the target value at 0.15. It's important to note that the target churn rate value will vary depending on the business sector. For instance, sectors like utility companies have low churn rates, so the target churn rate value should also be low. On the other hand, sectors like mobile phone providers have high churn rates, so the target churn rate value will be high.</p>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/7c4a2b10-d2a0-41cb-ac16-d613e404f29b">
</p>

</br>

<p align="justify"> If you're unable to access the dashboard, here's the final result after adding headers, modifying chart properties, adjusting colors and distribution, and including a Power Point background fill. Please note that the dynamic features of the charts are not available in this image. </p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/AlvaroM99/Power-BI---EndtoEnd-Customer-Churn-Analysis/assets/129555669/b2b42094-3a9b-4d64-b5f4-cc9d11cbcfd2">
</p>

</br>

### 6. Save & Publish Report to Power BI Service

<p align="justify"> Before publishing your dashboard, ensure that you save your work on your computer. To publish, sign up or log in and then click the "Publish" button on the "Home" tab. Typically, you'll upload your work to your workspace, which will load it into the Power BI Service app/browser. From there, you can export your dashboard, share it, and allow others to interact with it without making any alterations. </p>

</br>

## Conclusions

- <p align="justify"> First of all, the actual churn rate of the bank is surpassing the target churn rate that we decided was suitable for a bank-type business. So there must be something hiding in the data that is enhancing that churn rate. </p>
</br>
+ <p align="justify"> Let's go straight to the line and clustered column charts. In the first one, the customers and churn rate by age groups chart, we can clearly see a disproportionate increase in the churn rate when the customer is aged between 41 and 70. Although in the 41 to 50 stretch there is a significant quantity of customers and the churn rate is high, the main source of income comes from the 31 to 40 group in which the churn rate is relatively low compared with the number of customers; thus there's not too much to worry about. Of course, the churn rate peak in the 51 to 60 group is terrible, however, there are even fewer customers than in the stretch before. We can spot an issue with the older age groups but can not conclude anything for now. </p>
</br>
- <p align="justify"> According to the chart displaying the relationship between customers, churn rate, and credit score groups, it appears that customers who make fewer transactions and use their credit card sparingly are more likely to leave. This tendency could be due to the fact that older customers may not utilize all the benefits of credit cards, such as contactless payments or in-app investments. </p>
</br>
- <p align="justify"> The last chart, customers and churn rate by account balance groups, unveils some interesting insights. The customers leaving are either teenagers or university graduates creating new bank accounts or succesful professionals that have amassed a large amount of money. Hence, the bank is not providing taylor-made services for young people who are interested in connectivity, crypto-currency, stocks investment, or trading. Neither is provinding an attentive personalized service for its wealthier customers, which appreciate this the most.  </p>  
</br>
+ <p align="justify"> The distillation of the previously stated conclusion leads us to affirm that older customers with higher wealth status are leaving due to a lack of some kind of service that they might consider valuable, so they are moving to specialized banks for rich people. In addition, they are also losing its future customer basis as young people somehow create an account but they aren't able to keep them. </p>




