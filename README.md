# Marketing Campaign Performance Dashboard

# Introduction:
This report documents the process and methodology used to create an interactive Microsoft Power BI dashboard for analysing and monitoring digital marketing campaigns. The dataset contains campaign-level metrics such as Ad Spend, Impressions, Clicks, Conversions, Revenue, Category, and ROI (double-check vs dataset ROI) across multiple marketing channels and products.

## Table of Contents:
- [Introduction](#introduction)
- [Objective](#objective)
- [Dataset Overview](#dataset-overview)
- [Data Preparation Steps](#data-preparation-steps)
- [DAX Measures Created](#dax-measures-created)
- [New ROI Comparison Feature](#new-roi-comparison-feature)
- [Dashboard Visuals](#dashboard-visuals)

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


## DAX Measures Created:
<pre>
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
</pre>

![image_alt](https://github.com/Its-Lilianne/PBI-Project/blob/2b9c62e8e29f3c40699c84632841a9b1e1b92ff7/Image5.png)

#### *New ROI Comparison Feature:*
- Average ROI (Per Campaign): Shows average ROI across campaigns equally.
- Overall ROI is weighted by the size of campaigns, usually calculated from total revenue
and total ad spend, weighted by spend size; best for seeing total profitability. It is also
influenced more by large campaigns, allowing for deeper performance insights.

### Dashboard Visuals:
1. KPI Cards: Total Ad Spend, Impressions, Clicks, Conversions, Revenue, Overall ROI (weighted), Average ROI (per campaign)
2. Column Chart: Ad Spend by Marketing Channel
3. Column Chart: Clicks vs Impressions by Channel
4. Bar Chart: Conversion Rate by Category
5. Column Chart: Revenue by Product
6. Column Chart: Average ROI vs Overall ROI by Product
7. Line Charts: Time trends for Spend, Conversions, ROI, and Clicks

### Interactivity:
**Added slicers for:**
1. Campaign Date
2. Product Name
3. Product Category
4. Marketing Channel

![image_alt](https://github.com/Its-Lilianne/PBI-Project/blob/50812dae735cdbc4db7044a4e065a4523f5fb5a4/Dashboard%20.png)


### Insights:
- Certain channels (e.g., Influencer Marketing) yielded significantly higher ROI compared to others.
- Some products with lower ad spend still achieved high conversion rates, indicating strong organic appeal.
- Seasonal trends were observed, with specific months yielding better conversion and ROI performance.
- Conversion rate differences across product categories highlight areas for optimisation.

### Conclusion:
The Power BI dashboard provides an interactive and visual representation of marketing performance. With real-time filtering and KPI tracking, marketing teams can make data-driven decisions to optimise campaigns and budget allocation.

