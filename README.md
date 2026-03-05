# Loan Details Analysis and Performance Dashboard

## 📖 Table of Contents
- [Project Overview](#-project-overview)
- [Data Source](#-data-source)
- [Tools & Technologies](#-tools--technologies)
- [Data Cleaning & Preparation](#-data-cleaning--preparation)
- [Exploratory Data Analysis (EDA)](#-exploratory-data-analysis-eda)
- [Key Insights](#-key-insights) and Recommendations
- Conclusion

## 📊 Project Overview

This project focuses on analysing loan data to understand loan distribution, approval patterns, and financial trends. The dataset contains information such as loan amount, interest rate, loan term, loan status, state, and purpose of the loan. 

## Project Objective

The main objectives of this project are:

•	To analyse loan distribution across different states and purposes.

•	To evaluate loan approval and rejection patterns.

•	To study the relationship between loan amount and interest rate.

•	To identify trends in loan origination over time.

•	To create an interactive dashboard using Power BI for better decision-making.



## 🗂️ Data Source
•	Source Description and Timeline: https://practicedatasets.online/lending-club-datasets and 2023-2026

•	Domain: Banking and Financial Services

•  size : 782 KB

• key variables: Loan ID, Loan Amount, Interest Rate, Loan term (Months), purpose, Date, Loan Status, Default count, Monthly payment, State, Category. 

## 🛠️ Tools & Technologies

 - **Excel:** Data cleaning, transformation, and Pivot Tables.
 - **Power BI:** Data modelling, DAX calculations, visualization, and interactive dashboard creation.
 - **Documentation:** MS Word

## 🧹 Data Cleaning & Preparation

•	Standardized formats

•	Created calculated fields  

1.Default count =IF(D2="Default",1,0) 

2.Category = =IF([@[Loan Amount]]<20000, "Below Average", IF([@[Loan Amount]]<30000, "Average","Above Average")) 

•	Applied clean and Trim formulas to Purpose, Loan status and state columns.

•	Sorting: Sorted date column from Newest to oldest.

•	Converted the data into Fact and Dimension Table. Created 5 dimension tables.

1.	Dim State
2.	Dim Purpose
3.	Dim Status
4.	Dim Date
5.	Dim Category

• Connected fact and Dimension tables by Data modelling.
  
•	Extracted State ID, Purpose ID, Status ID, Date ID and Category ID from dimension tables to fact tables using Vlookup function.

E.g.,
         =VLOOKUP([@[Loan Amount Category]],Category[#All],2,FALSE) 
         
•	Likewise for all other columns. 

•	Kept only Numerical columns in fact table and removed the categorical columns for which dimension tables created.


## 🔍 Exploratory Data Analysis (EDA) 

•	Chart plotted to analyse the purpose for which maximum loan amount Sanctioned.

•	It shows the Debt Consolidation and Vacation contributes the most and Home Improvement contributes least.

•	It also varies for each State.

•	In the year 2025 only a greater number of loans sanctioned and more default loans but 2023 shows high paid off rate.

• The impact of interest rate in the loan status.

  	Default interest rate = 13.59, Paid off interest rate = 12.88
  	Current Interest rate = 13.07, Late interest rate = 13.46

 • Below average loan amount shows high sum of monthly payment compared to Average loan amount.

 • Same as monthly payment Below average category has greater loan term compared to Average and Above Average.

 • Top 10 states filtered by sum of default count from 50 states. This helps in analysing the Risk.


 <img width="1002" height="564" alt="image" src="https://github.com/user-attachments/assets/1d3fd750-8be8-4d6f-8639-544024fdbcba" /> 

 

 

 <img width="926" height="523" alt="image" src="https://github.com/user-attachments/assets/7e489c57-2398-4ee0-ad2b-43e2aca20320" /> 
 

 <img width="931" height="524" alt="image" src="https://github.com/user-attachments/assets/d086f83a-2771-42be-bdb8-b63007acd4ff" /> 


## 💡 Key Insights and Recommendations

•	In the year 2025 only a greater number of loans sanctioned and more default loans but 2023 shows high paid off rate. So, there might be a change in policies or strategies in collecting the loan across time. This needs to be corrected.

•	Default interest rate = 13.59, Paid off interest rate = 12.88
Current Interest rate = 13.07, Late interest rate = 13.46

The Interest rates clearly impact on the loan repayment. So, decreasing the interest rates may increase the loan closure %.

•	Below average loan amount shows high sum of monthly payment and loan terms compared to Average loan amount. Monthly payment amount and terms should be reduced based on the loan amount.

•	If the default count is rising, tightening credit score requirements may work specifically for those regions.

•	Lowering the maximum loan term for new applicants in those states will reduce long-term exposure.

## Conclusion:

The integration of Excel and Power BI proved effective for end-to-end data analysis, from raw data to visual reporting.
