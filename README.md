# cafe-sales-analysis

# Cafe Sales Data Analysis | Python & Pandas | Annual Sales Trends

## 1. Executive Summary

This project analyzes 10,000 cafe sales transactions to identify product performance, revenue trends, and data quality issues. The dataset contains inconsistent values, missing information, and fields that require cleaning before analysis. Using Python-based data cleaning, exploratory data analysis (EDA), and visualization, this project identifies key sales patterns and opportunities to improve inventory planning, promotional strategies, and transaction record accuracy.

## 2. Business Value & Questions Addressed

This analysis aims to support cafe operations and sales planning by answering the following business questions:

- **Product Performance:** Which products generate the highest revenue and sell the most units?
- **Revenue Trends:** Which months contribute the most revenue, and how does sales performance change throughout the year?
- **Weekly Sales Patterns:** Which days generate the highest and lowest revenue?
- **Product-Level Trends:** How does revenue for individual products vary from month to month?
- **Spending Behavior:** How are transactions distributed across low, medium, and high spending levels?
- **Data Quality:** How do missing values and inconsistent records affect the reliability of sales analysis?
- **Payment & Service Insights:** What patterns appear across payment methods and service locations?

## 3. Data Source & Architecture

### Data Source

- **Dataset:** Cafe Sales — Dirty Data for Cleaning Training
- **Source:** [Kaggle Dataset](https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training)
- **Record Count:** 10,000 transactions
- **Granularity:** One row represents an individual sales transaction.
- **Scope:** Annual sales records covering January through December 2023, based on the transaction dates in the dataset.
- **Data Quality Challenges:** Missing values, `UNKNOWN` and `ERROR` entries, inconsistent data types, and incomplete transaction details.

### Data Structure

The analysis uses a single transaction-level dataset with the following key fields:

| Column | Description |
|---|---|
| `Transaction ID` | Unique transaction identifier |
| `Item` | Product purchased |
| `Quantity` | Number of units purchased |
| `Price Per Unit` | Price per product unit |
| `Total Spent` | Total transaction value |
| `Payment Method` | Payment method used |
| `Location` | Service type, such as In-store or Takeaway |
| `Transaction Date` | Date of transaction |
| `Spending Level` | Low, Medium, or High spending category |
| `Day` | Day of the week |
| `Month` | Month of the transaction |

### Data Architecture

This project uses a single flat dataset rather than a multi-table relational database. Therefore, a multi-table Entity-Relationship Diagram (ERD) is not applicable.

```text
Cafe Sales CSV
      |
      v
Data Inspection
      |
      v
Data Cleaning & Type Conversion
      |
      v
Feature Engineering
(Spending Level, Day, Month)
      |
      v
Exploratory Data Analysis (EDA)
      |
      v
Sales Aggregation & Visualization
      |
      v
Business Insights & Recommendations
```

## 4. Tech Stack & Tools

- **Python:** Main programming language for data processing and analysis.
- **Pandas:** Used to inspect, clean, transform, group, and aggregate transaction data.
- **NumPy:** Supports numerical operations and data manipulation.
- **Matplotlib:** Creates charts to communicate sales performance and revenue trends.
- **Seaborn:** Produces heatmaps to compare product sales patterns across months and weekdays.
- **Jupyter Notebook:** Documents the analysis workflow, code, visualizations, and findings in one reproducible environment.

## 5. Key Insights & Actionable Takeaways

### Insight 1: Salad Leads Revenue Contribution, While Coffee Leads Sales Volume

Salad generates the highest total revenue among the analyzed products, while Coffee records the highest sales volume. This distinction shows that the product generating the most revenue is not necessarily the product purchased in the greatest quantity.

**Business implication:** Inventory and promotional decisions should consider both sales volume and revenue contribution. Coffee availability should be monitored to support demand, while Salad stock and product quality should be maintained to protect its revenue contribution.

![Revenue by Item](images/revenue-by-item.png)

![Quantity Sold by Item](images/quantity-sold-by-item.png)

### Insight 2: February Records an Unusually Strong Revenue Peak

February generates approximately 10,832 in total revenue, substantially exceeding the other months, which generally range from approximately 6,885 to 7,362. The monthly product heatmap also shows strong February revenue across several products, including Salad (1,970), Sandwich (1,664), Smoothie (1,578), and Juice (1,338).

**Business implication:** February represents a useful starting point for investigating sales growth drivers. The business should examine transaction volume, product mix, promotions, and other available operational records before deciding whether the same approach can be replicated in other months.

![Monthly Revenue Trend](images/monthly-revenue-trend.png)

![Monthly Revenue by Item](images/monthly-revenue-by-item.png)

### Insight 3: Monday Generates the Highest Daily Revenue, While Missing Transaction Details Limit Analysis

Monday records the highest total daily revenue at 16,342, while Wednesday records the lowest at 11,694. The dataset also contains substantial missing information in `Payment Method` and `Location`, with 2,579 and 3,265 missing records respectively, based on the initial data inspection.

**Business implication:** Monday may be a priority for inventory and staffing reviews. At the same time, improving transaction record completeness is important for understanding customer payment preferences and service-location performance. The observed patterns should be validated against transaction counts and data completeness before operational decisions are made.

![Revenue by Day](images/revenue-by-day.png)

## 6. Strategic Recommendations

1. **Prioritize inventory based on product performance.** Monitor Coffee sales volume and maintain the availability and quality of Salad, the leading revenue contributor.
2. **Investigate February's revenue peak.** Compare transaction volume, product mix, and any available promotion or operational records to identify factors behind the increase.
3. **Align operational planning with daily demand.** Review staffing and stock availability on Monday, while validating whether higher revenue is driven by more transactions or larger purchases.
4. **Improve transaction data completeness.** Review how payment method and service location are recorded, and consider requiring these fields where appropriate in the point-of-sale process.
5. **Validate missing-data patterns before drawing conclusions.** Compare missing-record rates across products, days, months, and service locations to determine whether the gaps follow a consistent pattern.
6. **Use revenue and quantity together.** Evaluate products using both revenue contribution and units sold rather than relying on a single performance measure.

## 7. How to Run

### Prerequisites

- Python 3
- Jupyter Notebook
- Pandas, NumPy, Matplotlib, and Seaborn

### Setup

1. Clone this repository:

   ```bash
   git clone https://github.com/YOUR-USERNAME/cafe-sales-data-analysis.git
   cd cafe-sales-data-analysis
   ```

2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. Place `Cafe_Sales.csv` in the project directory, or update the dataset path in the notebook.

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `cafe_project.ipynb` and run the cells from top to bottom.

### Suggested Repository Structure

```text
cafe-sales-data-analysis/
├── data/
│   └── Cafe_Sales.csv
├── images/
│   ├── revenue-by-item.png
│   ├── quantity-sold-by-item.png
│   ├── monthly-revenue-trend.png
│   ├── monthly-revenue-by-item.png
│   └── revenue-by-day.png
├── cafe_project.ipynb
└── README.md
```

*Note: Replace `YOUR-USERNAME` with your GitHub username and export the charts from the notebook into the `images/` directory before publishing. The image paths above are placeholders until those files are added.*
