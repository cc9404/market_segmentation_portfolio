# Strategic Segmentation of Top 100 US Independent Restaurants via K-Means

## Executive Summary
This project performs an unsupervised customer and business segmentation analysis on the top 100 highest-grossing independent restaurants in the United States. Using **K-Means Clustering**, restaurants are categorized based on two vital revenue drivers: **Average Check Size ($)** and **Total Annual Sales ($)**.

The analysis provides actionable insights for restaurant investors and market analysts into how different pricing strategies and revenue levels structure the elite dining market.

---

## Tech Stack & Libraries
* **Environment**: Jupyter Notebook (`ipykernel`)
* **Language**: Python 3.x
* **Data Manipulation**: `pandas`
* **Machine Learning**: `scikit-learn` (`KMeans`)
* **Visualization**: `matplotlib`

---

## Business Problem & Intuition
Top-line revenue ranking (`Rank`) alone fails to reveal how independent restaurants operate. A restaurant generating $20M in sales could be doing so through massive customer turnover at $35 per head, or through an exclusive high-end concept at $150 per head. 

By applying K-Means clustering on **Average Check** vs. **Sales**, we identify distinct business models and pricing tiers across the top 100 independent restaurants.

---

## Methodology & Analysis Workflow

1. **Feature Extraction**: Extracted `Average Check` ($x$) and `Sales` ($y$) to focus on unit pricing versus total gross revenue.
2. **Initial Exploration ($K=3$)**: Fitted a baseline K-Means model with 3 clusters to observe data distribution and initial centroids.
3. **Hyperparameter Tuning (Elbow Method)**: Evaluated Sum of Squared Errors (SSE / Inertia) across $K \in [2, 10]$. Identified a clear elbow point at **$K=4$**, which significantly reduced inertia before reaching diminishing returns.
4. **Final Model Execution ($K=4$)**: Re-trained the K-Means algorithm with 4 clusters and visualized final cluster boundaries and centroids.

---

## Cluster Profiles & Business Personas ($K=4$)

### 👑 Cluster 1: Mega-Volume Outliers (Top Tier)
* **Average Check**: ~$40–$45 | **Annual Sales**: ~$35M+
* **Key Concept**: Iconic, massive-capacity venues (e.g., *Carmine's Times Square*, *The Boathouse Orlando*) relying on massive guest throughput and high table turnover.

### 🌟 Cluster 2: High-Grossing Premium Venues
* **Average Check**: ~$85–$90 | **Annual Sales**: ~$22M–$28M
* **Key Concept**: Premium dining and nightlife flagships with strong pricing power and high guest volume.

### ⚖️ Cluster 3: Steady High-Performers
* **Average Check**: ~$75–$80 | **Annual Sales**: ~$17M–$20M
* **Key Concept**: Upper-middle tier casual and fine dining restaurants maintaining steady, profitable demand.

### 🏢 Cluster 4: Core Market Challengers
* **Average Check**: ~$50–$60 | **Annual Sales**: ~$11M–$15M
* **Key Concept**: Entry-level top-100 performers leveraging consistent neighborhood/urban foot traffic.

---

## Project Structure
```text
us_independent_restaurants_kmeans/
├── README.md                 # Project documentation
├── Independence100.csv       # Dataset
└── restaurant_kmeans.ipynb   # Interactive Jupyter Notebook
