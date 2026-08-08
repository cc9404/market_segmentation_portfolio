# Strategic Segmentation of Top 100 US Independent Restaurants via K-Means

## Executive Summary
This project performs an unsupervised customer/market segmentation analysis on the top 100 highest-grossing independent restaurants in the United States. Using **K-Means Clustering**, the analysis groups restaurants based on key operational and financial metrics—namely **Annual Sales**, **Average Check Amount**, and **Total Meals Served**. 

The primary goal is to uncover distinct business models within the independent restaurant industry, providing actionable strategic insights for investors, managers, and market analysts.

---

## Tech Stack & Libraries

* **Environment**: Jupyter Notebook (`ipykernel`)
* **Language**: Python 3.x
* **Data Manipulation**: `pandas`, `numpy`
* **Machine Learning**: `scikit-learn` (`KMeans`, `StandardScaler`)
* **Visualization**: `matplotlib`, `seaborn`

---

## Business Problem & Intuition
In the restaurant industry, high revenue can be achieved through vastly different strategies:
1. **High Volume, Low Check**: Massive guest capacity and fast table turnover at affordable prices.
2. **High Check, Low Volume**: Exclusive fine dining or luxury nightlife experiences with high price tags per guest.
3. **Balanced Mid-Market**: Steady foot traffic coupled with premium-casual pricing.

Evaluating performance purely by top-line revenue ranks masks these fundamental differences. Clustering allows us to categorize restaurants by their core revenue drivers and unit economics rather than just total scale.

---

## Dataset Overview
The analysis utilizes the `Independence100.csv` dataset, which contains metrics for the top 100 independent US restaurants:

* **Rank**: Top-line revenue ranking (1 to 100).
* **Restaurant**: Name of the establishment.
* **Sales ($)**: Total annual sales volume.
* **Average Check ($)**: Average expenditure per guest.
* **Meals Served**: Total annual guest count / meal covers.
* **City & State**: Geographical location.

---

## Methodology & Pipeline

### 1. Feature Engineering & Preprocessing
* **Feature Selection**: Selected core numerical features (`Sales`, `Average Check`, `Meals Served`).
* **Feature Scaling**: Applied `StandardScaler` to standardize features to a mean of 0 and variance of 1, ensuring equal weight across scale-sensitive features during distance calculations.

### 2. K-Means Clustering & Model Evaluation
* **Elbow Method (Inertia)**: Plotted Sum of Squared Errors (SSE) across various $K$ values to find the optimal point of diminishing returns.
* **Silhouette Analysis**: Evaluated cluster cohesion and separation quality to validate the chosen $K$.

---

## Key Clusters & Business Personas

*(Note: Update the values and descriptions below based on your specific notebook outputs/centroids)*

### 🏆 Cluster 0: Mass-Market Volume Giants
* **Characteristics**: Low to moderate average check ($30 - $45), extremely high meals served (>500k/year).
* **Primary Driver**: High capacity, high table turnover, iconic tourist locations.
* **Strategic Focus**: Maximizing throughput, labor efficiency, and floor operations.

### 💎 Cluster 1: Luxury Fine Dining & Nightlife
* **Characteristics**: Extremely high average check ($90 - $190+), lower volume (<200k/year).
* **Primary Driver**: Premium pricing, upscale atmosphere, high-margin beverages and experience.
* **Strategic Focus**: Guest retention, brand exclusivity, premium experience enhancement.

### ⚖️ Cluster 2: Balanced Urban Flagships
* **Characteristics**: Mid-to-high average check ($50 - $85), moderate to high guest volume.
* **Primary Driver**: Steady urban demand, premium-casual dining experience.
* **Strategic Focus**: Upselling menu items, optimizing off-peak booking times.

---

## Strategic Actionable Insights
* **For Investors**: Benchmark new independent ventures against these clusters to set realistic operational targets (e.g., target check size vs. necessary table turnover).
* **For Operators**: Identify whether a restaurant is underperforming relative to its cluster peer group (e.g., a luxury venue with below-average check size).

---

## Project Structure
```text
us_independent_restaurants_kmeans/
├── README.md               # Project documentation
├── data/
│   └── Independence100.csv # Dataset
└── notebooks/
    └── restaurant_kmeans.ipynb # Interactive Jupyter Notebook
