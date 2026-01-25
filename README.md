# Customer Segmentation & Behavioral Analysis (RFM + K-Means)

## Project Overview

This project analyzes a dataset of **500,000+ online retail transactions** to identify distinct customer segments. By using **RFM (Recency, Frequency, Monetary) Analysis** and **K-Means Clustering (Machine Learning)**, we transformed raw transaction data into actionable business insights.

The goal is to help the marketing team target specific customer groups (e.g., "Champions" vs. "At Risk") to improve retention and maximize revenue.

## Business Goal

- **Identify High-Value Customers:** Who contributes the most to revenue?
- **Churn Prevention:** Who hasn't purchased in a long time?
- **Targeted Marketing:** How can we group customers mathematically to personalize campaigns?

## Tech Stack

- **Python:** Main programming language.
- **Pandas:** Data manipulation and aggregation.
- **Scikit-Learn:** Machine Learning (K-Means Clustering, StandardScaler).
- **Matplotlib & Seaborn:** Static visualizations (Distribution, Scatter plots).
- **Plotly:** Interactive visualizations (Geographic Maps, 3D Clusters).

## Dataset

- **Source:** [UCI Machine Learning Repository - Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii)
- **Description:** Transactions occurring between 01/12/2010 and 09/12/2011 for a UK-based and registered non-store online retail.
- **Key Columns:** `InvoiceDate`, `Price`, `Quantity`, `Customer ID`, `Country`.

---

## Methodology

### 1. Data Cleaning

- Removed rows with missing `Customer ID` (cannot segment unknown users).
- Filtered out cancelled transactions (Invoice numbers starting with 'C').
- Calculated `Total Price` (`Quantity` \* `Price`).

### 2. RFM Analysis (Rule-Based)

We calculated three key metrics for each customer:

- **Recency:** Days since last purchase.
- **Frequency:** Total number of transactions.
- **Monetary:** Total revenue contributed.

Customers were scored from 1-4 using Quantiles, creating segments like "Champions", "Potential Loyalists", and "At Risk".

### 3. Machine Learning (K-Means Clustering)

To validate the manual segmentation, we used Unsupervised Learning:

1.  **Log Transformation:** Handled skewed data distribution.
2.  **Standard Scaling:** Normalized data to Mean=0, Std=1.
3.  **Elbow Method:** Determined the optimal number of clusters (K=3).
4.  **K-Means Algorithm:** Mathematically grouped customers into 3 distinct personas.

---

## Visualizations

All visualizations are stored in the `visualizations/` folder.

|   Visualization    | Insight                                                                                    |
| :----------------: | :----------------------------------------------------------------------------------------- |
| **Revenue Trend**  | 30-Day Moving Average reveals the underlying growth trend, smoothing out daily volatility. |
| **Geographic Map** | Interactive Plotly map showing revenue concentration in the UK vs. International markets.  |
|  **3D Clusters**   | 3D scatter plot visualizing the mathematical separation between VIPs and Casual buyers.    |
|    **Treemap**     | Hierarchical view of how much revenue each Customer Segment contributes.                   |

### Example: Customer Segments

_(You can upload your `segment_distribution.png` to GitHub and link it here)_
![Customer Segments](visualizations/segment_distribution.png)

---

## How to Run

1.  **Clone the Repository**

    ```bash
    git clone [https://github.com/nameisnamish/RFM_Customer_Segmentation.git](https://github.com/nameisnamish/RFM_Customer_Segmentation.git)
    cd RFM_Customer_Segmentation
    ```

2.  **Install Dependencies**

    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Analysis**
    Open `notebooks/rfm_analysis.ipynb` in Jupyter Notebook or VS Code and run all cells.

---

## Key Insights

1.  **Pareto Principle:** The top 20% of "Champion" customers generate nearly 60% of the total revenue.
2.  **Churn Risk:** A significant portion of the user base has high Frequency but low Recency, indicating they are "At Risk" of leaving.
3.  **Seasonality:** Sales trends show a clear spike in Q4 (November/December), aligning with holiday shopping behaviors.

---

## Contact

- **Name:** Namish M S
- **LinkedIn:** www.linkedin.com/in/namish-m-s-9b2b41346

