**Exam2 Sales Prediction Notebook**
This Jupyter notebook performs exploratory data analysis and builds predictive models for sales data from "messysales - Sheet1.csv".

**Dataset Overview**
Loaded a dataset with 200 rows covering sales across regions (North, East, South, West), categories (Electronics, Gadgets), products, units sold, unit prices, total sales, and profit margins. Data spans 2024 dates with some inconsistencies like mixed formats and missing values

**Data Cleaning Steps**
Standardizes date formats using pd.to_datetime with mixed parsing.
Parsed text numbers in Units Sold via word2number library.
Cleaned Profit Margin by extracting numeric values with regex.
Normalized categories and regions (e.g., title case, replaces variants like "ELEC" to "Electronics").
Droped rows with nulls in key columns (Total Sales, Units Sold) and removes redundant "Product" column.

**Exploratory Analysis**
Checked info, described stats, nulls, uniques.
Visualized profit margins by category with boxplots.
Displayed cleaned data head and summaries

**Modeling Pipeline**
Prepared features: one-hot encodes "Category" and "Region", selects numeric columns.
Splits data 80/20 train/test (random_state=42).
Trained Linear Regression (MAE ~3,924, R² 0.834) and Random Forest (MAE ~1,936, R² 0.943).
Compared models in table; Random Forest superior.
Feature importances bar chart (via Random Forest).
