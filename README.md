# 🛒 Groceries Transaction Analysis & Market Basket Modeling

This notebook performs data transformation, analysis, and modeling on a grocery transactions dataset using a combination of exploratory data analysis, association rule mining, and clustering.

---

## 📦 Dataset

- Source: `GroceriesInitial.csv`
- Downloaded via Google Drive using `gdown`.

---

## 🧰 Libraries Used

- **pandas**, **numpy** – data handling and manipulation
- **matplotlib**, **seaborn** – data visualization
- **mlxtend** – for market basket encoding
- **apyori** – Apriori algorithm for association rule learning
- **scikit-learn** – KMeans clustering

---

## 📊 Data Exploration

- Initial descriptive statistics and data browsing
- Key visualizations:
  - Histogram of `basket_value`
  - Histogram of `recency_days`
  - Scatter plot of `basket_value` vs `recency_days`

---

## 🛍️ Association Rule Mining

- Extracted a list of item-based transactions.
- Filtered to focus on relevant items.
- Encoded the data to a binary format using `TransactionEncoder`.
- Categorized basket values into:  
  `low_value_basket`, `medium_value_basket`, `high_value_basket`

### Association Rules:

- Applied the **Apriori** algorithm with various `min_support` values.
- Sorted resulting rules by **confidence**.
- Notable insight:
  - Products like `sausage` appear frequently in **high-value baskets**.
  - Combinations such as `[whole milk, pastry]` are strongly tied to specific customer segments.

---

## 📈 K-Means Clustering

- Used features: `basket_value` and `recency_days`
- Clustered data into **5 customer segments**
- Visualized clusters with centroids
- Described segments:
  - e.g., “Recent high-value buyers” vs “Older, moderate-value buyers”

---

## 🔁 Combined Analysis

- Merged **item-level data**, **cluster labels**, and **basket categories**
- Ran Apriori again to find rules like:
  - `[cluster=2] → [medium_value_basket]`
  - `[sausage, cluster=3] → [high_value_basket]`
- These insights can support **targeted marketing** and **recommendation systems**

---

## 📌 Summary of Insights

- Cluster 0 (older, high-value buyers) should be a **priority for marketing**
- `Pastry` may be underperforming and driving loss of repeat purchases
- Rules identify product affinities and help personalize offerings

---

## 🚀 Getting Started

1. Clone the repository or download the notebook and `requirements.txt`.

2. Create and activate a virtual environment (optional but recommended):
3. Install all required dependencies using:
4. Launch Jupyter Notebook and run the notebook:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook

```
