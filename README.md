

[![Open In Power Bi](https://img.shields.io/badge/open_in_power_bi-F2C811?style=for-the-badge\&logo=powerbi\&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiMTQ1YjJiODctNmJjMS00NGYwLWFjMWEtNGE5YzdkYWUyYzIwIiwidCI6ImFlZDI3MWNkLTYzOTgtNDllZi1hOWNmLTQ4NDIyMTAxZTE0ZSIsImMiOjEwfQ%3D%3D)

# Pharmaceutical Sales Analysis

This project explores raw sales data from a multinational pharmaceutical producer and transforms it into actionable insights through an interactive PowerBI report.

<img 
src="https://cuspera-category-images.s3.us-east-2.amazonaws.com/image_sales-analytics-v10.png" 
width="1000"
height="500"
/>

---

## Features

⚡ **PowerBI Desktop** for report development
⚡ **PowerQuery Editor** for cleaning, shaping, and modeling data
⚡ **PowerBI Service** to host the report online without requiring desktop access
⚡ **Multi-page interactive dashboards** for drilldowns and performance analytics

---

## Table of Contents

* [Introduction](#introduction)
* [Objective](#objective)
* [Dataset](#dataset)
* [Solution Approach](#solution-approach)
* [How To Use](#how-to-use)
* [License](#license)
* [Credits](#credits)
* [Get in touch](#get-in-touch)

---

## Introduction

* `Datamatrix-ml Pharmaceuticals` is an established global player in the drug manufacturing sector.
* Markets are organized region-wise, and this dataset focuses on a region covering Germany & Poland.
* Sales aren't direct-to-consumer; distribution partners handle product supply in each region.
* Distributors share retail-level sales data via CSVs, which the company uses for performance analysis.

---

## Objectives

The task is to analyze historical sales data and provide business intelligence dashboards for different stakeholders. Below are the key needs:

| Requirement ID | For Whom                | Requirement Description                                                                                                                                                         |
| :------------- | :---------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| DM-DA01-REQ-1  | Executive Committee     | A consolidated view of overall performance across years, months, channels, product class, and geography. Should highlight top cities, products, and product classes by revenue. |
| DM-DA01-REQ-2  | Sales Manager/Sales Rep | A detailed breakdown of performance across distributors, customers, product lines, and top buyers. Should display segment-level sales patterns.                                 |
| DM-DA01-REQ-3  | Head of Sales           | A deep dive into sales contribution by teams and reps, including best-performing managers, reps, and product lines. Reports should support time-based filtering.                |

***Table-1 : Requirements***

---

## Dataset

Data was collected from multiple distributors and contains wholesale-to-retail transactions. The raw dataset `pharma-data.csv` is available here:
📂 [Download Dataset](https://drive.google.com/file/d/1npKF_C2tG5psY-at4wvpEgh6T-7KHxEZ/view?usp=share_link)

| Field             | Description                       |
| :---------------- | :-------------------------------- |
| Distributor       | Name of wholesaler                |
| Customer Name     | Name of customer                  |
| City              | Customer city                     |
| Country           | Customer country                  |
| Latitude          | Geo coordinate                    |
| Longitude         | Geo coordinate                    |
| Channel           | Type of buyer (Hospital/Pharmacy) |
| Sub-channel       | Sector (Gov/Private/etc.)         |
| Product Name      | Drug Name                         |
| Product Class     | Category (e.g., Antibiotics)      |
| Quantity          | Units sold                        |
| Price             | Selling price                     |
| Sales             | Revenue                           |
| Month             | Month of transaction              |
| Year              | Year of transaction               |
| Name of Sales Rep | Representative handling sale      |
| Manager           | Rep's manager                     |
| Sales Team        | Assigned team                     |

***Table-2 : Data Definition***

---

## Solution Approach

| Requirement ID | Solution ID   | Proposed Solution                                                                                                           |
| :------------- | :------------ | :-------------------------------------------------------------------------------------------------------------------------- |
| DM-DA01-REQ-1  | DM-DA01-SOL-1 | Create an `Executive Summary` dashboard presenting high-level KPIs with time-based filtering.                               |
| DM-DA01-REQ-2  | DM-DA01-SOL-2 | Create a `Distributor & Customer Insights` dashboard for buyer-level analysis and product drilldowns.                       |
| DM-DA01-REQ-3  | DM-DA01-SOL-3 | Develop a `Sales Team Performance` dashboard showing contribution by managers, reps, and products, with year/month slicers. |

***Table-3 : Proposed Solution***

---

### Exploratory Data Analysis (EDA) — *pandas*

Initial data inspection was done in a Jupyter notebook using `pandas` to validate structure and quality:

* Checked missing values
* Identified outliers
* Verified sales (fixed negative values if applicable)
* Classified numerical and categorical fields
* Reviewed column uniqueness and ranges

These steps could be done in Excel or PowerQuery, but pandas is faster and scalable for large files.

---

### Data Cleaning & Transformation — *PowerQuery*

Minimal cleanup was needed as data was structured well:

* Column headers standardized
* Appropriate data types assigned
* Prepared fields for modeling

---

### Data Model — *PowerBI Desktop*

The dataset contained both dimensions and facts in one table. A star schema was built by splitting them and defining relationships.

<img src="https://github.com/aryansingh2206/Sales-Performance-Dashboard/blob/master/images/data-model.png"/>

Dimension tables are prefixed with `DIM`, and the sales table is represented as `FACT`.

---

### Report Pages

#### **1️⃣ Executive Summary**

Overall performance indicators with drill-down capability.

<img src="https://github.com/aryansingh2206/Sales-Performance-Dashboard/blob/master/images/dist-cust-analysis-page.png"/>

#### **2️⃣ Distributor & Customer Analysis**

Focuses on buyer behavior and sales contribution by distributors and cities.

<img src="https://github.com/aryansingh2206/Sales-Performance-Dashboard/blob/master/images/pharma-feature-image.png"/>

#### **3️⃣ Sales Team Performance**

Breakdown by teams, managers, and individual reps.

<img src="https://github.com/aryansingh2206/Sales-Performance-Dashboard/blob/master/images/sales-team-perform-page.png"/>

---

## How To Use

### **View Online (Recommended)**

[![Open In Power Bi](https://img.shields.io/badge/open_in_power_bi-F2C811?style=for-the-badge\&logo=powerbi\&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiMTQ1YjJiODctNmJjMS00NGYwLWFjMWEtNGE5YzdkYWUyYzIwIiwidCI6ImFlZDI3MWNkLTYzOTgtNDllZi1hOWNmLTQ4NDIyMTAxZTE0ZSIsImMiOjEwfQ%3D%3D)

### **Edit in PowerBI Desktop**

Download `pharma-analysis.pbix` and open it locally. The model includes transformed data, so no separate dataset import is required.

---


## Credits

* Dataset from [Foresight BI](https://foresightbi.com.ng/practice-data/3-datasets-for-your-portfolio/)

---


