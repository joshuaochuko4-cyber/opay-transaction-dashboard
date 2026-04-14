# opay-transaction-dashboard
Personal Finance Dashboard built with Power BI and Excel — 10,828 OPay transactions analyzed
# OPay Personal Finance Dashboard

## Overview
An end-to-end personal finance analytics project built using my real 
OPay bank statement data covering January to December 2025.

## Dataset
- Source: Personal OPay bank statement export
- Wallet Account Transactions: 7,006 rows
- Savings Account Transactions: 3,822 rows
- Total Transactions: 10,828
- Total Transaction Value: ₦126M+

## Tools Used
- Microsoft Excel — Data cleaning & transformation
- Microsoft Power BI — Dashboard design & DAX measures
- Power Query (M Language) — Table appending & data typing
- DAX — 20+ custom measures
- PowerPoint — Dashboard wireframe & mockup

## Data Cleaning Steps (Excel)
- Removed 6 metadata rows from both sheets
- Replaced "--" placeholders with zeros
- Converted text-formatted numbers to actual numbers
- Used TRIM() to clean trailing whitespace from all descriptions
- Built Transaction_Type and Category classification columns
- Added Account_Type column to distinguish Wallet vs Savings
- Converted both sheets to Excel Tables

## Data Modelling (Power BI)
- Appended Wallet + Savings into one Transactions table
- Built dynamic DAX Date Table with Year, Month, Quarter, Day columns
- Created Many-to-One relationship between DateTable and Transactions
- Wrote 20+ DAX measures

## Key DAX Measures
- Total Credit = CALCULATE(SUM(Transactions[Credit_NGN]), Transactions[Transaction_Type] = "Credit")
- Total Debit = CALCULATE(SUM(Transactions[Debit_NGN]), Transactions[Transaction_Type] = "Debit")
- Net Flow = [Total Credit] - [Total Debit]
- Transaction Count = COUNTROWS(Transactions)
- MoM Credit Growth = DIVIDE([Total Credit] - CALCULATE([Total Credit], DATEADD(DateTable[Date],-1,MONTH)), CALCULATE([Total Credit], DATEADD(DateTable[Date],-1,MONTH)))

## Dashboard Features
- 4 KPI Cards — Total Credit, Total Debit, Net Balance, Total Transactions
- Monthly Trend — Credit vs Debit bar chart Jan–Dec
- Balance Trend — Line chart across the full year
- Transaction by Channel — Mobile, USSD, WEB
- Transactions by Day — Mon→Sun sorted column chart
- Transactions by Category — Donut chart breakdown
- 4 Interactive Slicers — Date, Category, Account Type, Channel

## Key Insights
- Processed ₦126M+ across 10,828 transactions in 2025
- Mobile channel accounted for 95%+ of all transactions
- Withdrawals dominated at 58.47% of all categories
- Significant balance spike recorded in September 2025
- Weekdays showed consistently higher transaction volumes than weekends

## Dashboard Preview
![Dashboard](![image](https://github.com/user-attachments/assets/cdc6c9cb-1e0d-4975-bab7-cbf50468f956)


)

## Author
Isah Joshua Ochuko
Data Analyst | Lagos, Nigeria
