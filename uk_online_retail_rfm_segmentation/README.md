# UK Online Retail Customer Segmentation via RFM Analysis

## Executive Summary
This project performs customer segmentation analysis on UK transactions from the UCI Online Retail dataset. Using **RFM Analysis**, customers are scored based on **Recency**, **Frequency**, and **Monetary Value** to identify high-value customer groups and support targeted marketing strategies.

The analysis identifies **409 high-value customers** with an `RFMScore` of `111`, representing the most recent, frequent, and highest-spending customer segment.

---

## Tech Stack & Libraries
- **Environment**: Jupyter Notebook (`ipykernel`)
- **Language**: Python 3.x
- **Data Manipulation**: `pandas`, `numpy`
- **Visualization**: `matplotlib`
- **Data Source**: [UCI Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)

---

## Business Problem & Intuition
Retail customers do not contribute equal value to a business. Some customers purchase frequently and spend significantly, while others may be inactive or have low purchasing value.

By applying RFM scoring, this project identifies customer groups based on purchase recency, transaction frequency, and total spending. These segments can support loyalty programs, retention campaigns, and personalized marketing efforts.

---

## Methodology & Analysis Workflow

1. **Data Cleaning**: Filtered transactions to the United Kingdom, removed missing customer IDs, and retained positive quantities and unit prices.
2. **Feature Engineering**: Created `TotalPrice` by multiplying `Quantity` by `UnitPrice`.
3. **Customer-Level Aggregation**: Calculated Recency, Frequency, and Monetary value for 3,920 customers.
4. **RFM Scoring**: Applied quartile-based scoring from 1 to 4 for each RFM metric.
5. **Customer Segmentation**: Combined the three scores into an `RFMScore`, where `111` represents the highest-value customer group.
6. **Visualization**: Created a 3D scatter plot to show customer distribution across RFM score dimensions.

---

## RFM Metrics

| Metric | Definition |
|---|---|
| **Recency** | Days since a customer's most recent purchase |
| **Frequency** | Number of transaction records per customer |
| **Monetary** | Total customer spending (`Quantity × UnitPrice`) |

---

## Key Findings

- **354,321** valid UK transaction records were analyzed.
- **3,920** customers were included in the RFM table.
- **409** customers received an `RFMScore` of `111`.
- The `111` segment represents recent, frequent, and high-spending customers.
- This group is a strong target for loyalty rewards, exclusive offers, and retention campaigns.

---

## Project Structure

```text
uk_online_retail_rfm_segmentation/
├── README.md                 # Project documentation
├── Online Retail.xlsx        # Dataset
└── rfm_customer_segmentation.ipynb  # Interactive Jupyter Notebook
