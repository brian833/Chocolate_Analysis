# 📦 Chocolate Sales Performance Dataset

This dataset contains detailed records of sales performance including quantities shipped, sales amounts, product categories, and regional sales breakdowns. It's ideal for data analysis, visualization, business intelligence, and time series forecasting.

---

## 📁 Dataset Contents

The downloaded ZIP file includes:

- `sales_data.csv` — Contains transactional sales records
- `README.md` — Overview and usage instructions

---

## 🧾 Columns

| Column Name        | Description                             |
|--------------------|-----------------------------------------|
| Date               | Date of sale or shipment                |
| Salesperson        | Name of the salesperson                 |
| Product            | Name of the product                     |
| Country            | Destination country                     |
| Boxes Shipped      | Number of boxes shipped                 |
| Sales              | Sales revenue from the transaction ($)  |

> Please adjust if your actual file has different columns.

---

## 🧠 Possible Use Cases

- 📊 Data visualization with Matplotlib, Seaborn, or Plotly
- 📈 Time series decomposition and forecasting
- 📍 Country-wise or product-wise performance analysis
- 🧮 Outlier detection and cleaning
- 💡 Machine learning feature engineering

---

## 🔍 Sample Analysis Ideas

- **Monthly Sales Trends**
- **Top Selling Products**
- **Sales per Country**
- **Performance per Salesperson**
- **Average Boxes Shipped**
- **Outlier Detection in Sales**

---

## 🚀 Getting Started

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('sales_data.csv')

# Convert 'Date' column to datetime
df['Date'] = pd.to_datetime(df['Date'])

# Group monthly sales
df['Month'] = df['Date'].dt.to_period('M')
monthly_sales = df.groupby('Month')['Sales'].sum()

# Plot
monthly_sales.plot(kind='line', marker='o')
plt.title("Monthly Sales Trend")
plt.xlabel("Month")
plt.ylabel("Total Sales ($)")
plt.grid(True)
plt.show()
