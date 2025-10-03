# Marketing Campaign Performance Dashboard

# Introduction:
This report documents the process and methodology used to create an interactive Microsoft Power BI dashboard for analysing and monitoring digital marketing campaigns. The dataset contains campaign-level metrics such as Ad Spend, Impressions, Clicks, Conversions, Revenue, Category, and ROI (double-check vs dataset ROI) across multiple marketing channels and products.

## Table of Contents:

- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Objective](#objectives)
- [Key Business Questions](#key-business-questions)
- [Tools and Methodologies](#tools-and-methodologies)

## Objective:
The goal was to design a clean, interactive, and professional dashboard that presents key marketing KPIs, allows filtering by multiple dimensions, and clearly communicates ROI differences across channels and campaigns, providing actionable insights to optimise future campaigns.

### Dataset Overview:
- 1,000 campaign records
- Columns:
  1. Campaign ID
  2. Product Name
  3. Category
  4. Ad Spend (INR)
  5. Impressions
  6. Clicks
  7. Conversions
  8. Revenue (INR)
  9. ROI
  10. Campaign Date
  11. Marketing Channel - Covers various marketing channels such as Email Campaign, Instagram Ads, and Influencer Marketing



### Data Preparation Steps:
1. Loaded CSV file into Power BI.
2. Verified and corrected data types (dates, numbers, text).
3. Checked for missing values and ensured data consistency.


![image alt](https://github.com/Its-Lilianne/PBI-Project/blob/9d7cce81e3acfbe2511be08c976e112139e2ddd2/Image1.png)

![image_alt](https://github.com/Its-Lilianne/PBI-Project/blob/205c7e31cf6f8136e3d7818f235f1e91af8f2a65/Image2.png)

![image_alt](https://github.com/Its-Lilianne/PBI-Project/blob/8049d49ef913409430177ffbf6ddee102daf5def/Image6.png)

![image_alt](https://github.com/Its-Lilianne/PBI-Project/blob/13f3378f75c83be32f47f0eb0a09ad7dc0b461ef/Image4.png)


##DAX Measures Created:
1. Total Ad Spend = SUM('PBI_Marketing_Data'[Ad Spend (INR)])
2. Total Impressions = SUM('PBI_Marketing_Data'[Impressions])
3. Total Clicks = SUM('PBI_Marketing_Data'[Clicks])
4. Total Conversions = SUM('PBI_Marketing_Data'[Conversions])
5. Total Revenue = SUM('PBI_Marketing_Data'[Revenue (INR)])
6. Average ROI (Dataset ROI) = AVERAGE('PBI_Marketing_Data'[ROI])
7. Overall ROI (Double-check) = DIVIDE(
SUM('PBI_Marketing_Data'[Revenue (INR)]) -
SUM('PBI_Marketing_Data'[Ad Spend (INR)]),
SUM('PBI_Marketing_Data'[Ad Spend (INR)]), 0) * 100
8. CTR (%) = DIVIDE(
SUM('PBI_Marketing_Data'[Clicks]),
SUM('PBI_Marketing_Data'[Impressions]), 0) * 100
9. Conversion Rate (%) = DIVIDE(
SUM('PBI_Marketing_Data'[Conversions]),
SUM('PBI_Marketing_Data'[Clicks]), 0) * 100
