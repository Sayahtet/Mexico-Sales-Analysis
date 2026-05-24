# Mexico Toy Store Sales Analysis

## 📌 Project Overview

This project performs an **end‑to‑end exploratory data analysis (EDA)** on the **Maven Toys Mexico** dataset using **Python** and **pandas**. The goal is to uncover sales patterns, product performance, store‑level insights, and profitability drivers for a toy store chain across Mexico.

The analysis covers:
- Data cleaning and merging of multiple CSV files
- Revenue and profit calculations
- Product‑category and individual product performance
- Store and city‑level revenue ranking
- Time series trends (monthly, weekly, and daily)
- Identification of low‑performing products and stores

> 📓 **Notebook:** `Mexico_toy_store.ipynb`

---

## 📂 Dataset

The data comes from **Maven Toys** and consists of five CSV files:

| File | Description |
|------|-------------|
| `sales.csv` | Transaction records (Sale_ID, Date, Store_ID, Product_ID, Units) |
| `products.csv` | Product details (Product_ID, Name, Category, Cost, Price) |
| `stores.csv` | Store information (Store_ID, Name, City, Location, Open Date) |
| `inventory.csv` | Stock‑on‑hand per store per product |
| `calendar.csv` | Date reference table (not heavily used) |
| `data_dictionary.csv` | Column definitions |

**Data size:** ~829,000 sales records (2022–2023).

---

## 🔧 Tools & Libraries

- **Python 3.13**
- **pandas** – data manipulation & aggregation
- **NumPy** – numerical operations
- **Matplotlib** – basic visualizations (optional)

All analysis is done in a single Jupyter Notebook.

---

## 📊 Analysis Steps

1. **Data Loading & Inspection**  
   - Load all CSV files into pandas DataFrames.
   - Check data types, missing values, and basic info.

2. **Data Cleaning & Merging**  
   - Merge `sales` with `products` → `sale_prod`
   - Merge `sale_prod` with `stores` → `toy_sales` (final working DataFrame)
   - Convert `Date` to datetime.
   - Remove dollar signs (`$`) from `Product_Price` and `Product_Cost` and convert to float.

3. **Feature Engineering**  
   - `Revenue = Units * Product_Price`
   - `Profit = Revenue - Product_Cost * Units`

4. **Product Analysis**  
   - Total revenue & profit by product category.
   - Top 10 products by revenue, profit, and units sold.
   - Profit margin calculation and ranking.
   - Identification of **low‑sales & high‑price** products.

5. **Store & City Analysis**  
   - Revenue by store and city.
   - Group stores into **High / Mid / Low / Lowest** revenue quartiles.
   - Profit margin by city.

6. **Time Series Analysis**  
   - Monthly revenue and profit trends.
   - Week‑over‑week and day‑of‑week performance.
   - Month‑over‑month percentage change.

7. **Pivot Tables**  
   - Revenue by store vs product category.
   - Revenue by month vs product.

---

## 🔍 Key Insights (Executive Summary)

### Overall Performance
- **Total Revenue:** $14,444,572  
- **Total Profit:** $4014029.0 
- **Overall Profit Margin:** ~27.79%

### Product‑Level
- **Colorbuds** is the star product:  
  - 104,368 units sold, $1.05M profit, **53% profit margin**  
  - Contributes **20%** of total profit
- **Toys** category generates the highest revenue ($5.09M), but **Electronics** has the highest margin (45%).
- **Four products** (Colorbuds, Lego Bricks, Action Figure, Magic Sand) account for **37%** of total profit.
- **Low‑sale / high‑price products** (PlayDoh Playset, Plush Pony, Monopoly, Mini Basketball Hoop) need promotional attention.

### Store & City
- **Ciudad de Mexico** is the top‑performing city:  
  - $1.65M revenue, $465k profit, 28% margin
- **Downtown** stores outperform Commercial, Residential, and Airport locations.
- **Maven Toys Campeche 2** is the lowest‑revenue store ($206k) – requires operational review.

### Time Trends
- **December 2022** was the best month ($877k revenue, $246k profit).
- **March 2023** also strong ($883k revenue, $231k profit).
- **August** is consistently the lowest‑sales month across both years.
- **Saturdays** and **Fridays** are the best‑performing weekdays.

---

## ▶️ How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/Sayahtet/mexico-toy-store-analysis.git
   cd mexico-toy-store-analysis
Install required libraries

bash
pip install pandas numpy matplotlib
Place the dataset
Download the Maven Toys dataset (CSV files) and place them in a folder.
Update the file paths in the notebook accordingly.

Run the Jupyter Notebook

bash
jupyter notebook Mexico_toy_store.ipynb
Or use VS Code / Google Colab.

📁 Repository Structure
text
.
├── Mexico_toy_store.ipynb   # Main analysis notebook
├── README.md                # This file
└── data/                    # (optional) folder for CSV files – not included
Note: The dataset is not included due to size and licensing. You can obtain it from Maven Analytics (free registration).

📌 Recommendations for the Business
Stock Colorbuds aggressively – it’s the best‑selling and most profitable product.

Promote Electronics (e.g., Gamer Headphones) – they have the highest profit margin.

Investigate why August sales drop every year – plan seasonal promotions.

Support low‑sales cities (La Paz, Cuernavaca, Durango) with local marketing campaigns.

Review operations at Maven Toys Campeche 2 – the lowest‑revenue store.

Consider discounting or bundling low‑sale / high‑price items (PlayDoh Playset, Monopoly).

🙋‍♀️ Author
Sayahtet – [www.linkedin.com/in/htet-aung-myint-46a4a6313]

This project was completed as part of a personal portfolio to demonstrate data cleaning, aggregation, and business insight generation using pandas.

## 📊 Power BI Dashboard – Interactive Version

Due to my **student Power BI account** restrictions, the dashboard cannot be published publicly.  
However, you can see a full preview below:

![Dashboard Preview]<img width="1360" height="670" alt="Screenshot 2026-05-24 155733" src="https://github.com/user-attachments/assets/cc14245b-c156-4957-b805-de45f9c11872" />
<img width="1445" height="758" alt="Screenshot 2026-05-22 034445" src="https://github.com/user-attachments/assets/a08dc1d5-191b-4d46-a8ea-0fcfe061dcf7" />
<img width="1454" height="786" alt="Screenshot 2026-05-22 034437" src="https://github.com/user-attachments/assets/26d4296a-4979-4e61-812f-3e37a7662a22" />
<img width="1555" height="827" alt="Screenshot 2026-05-22 034414" src="https://github.com/user-attachments/assets/b2da315d-c66e-4c83-aa44-eb57de92fba5" />



> 🔍 **What the dashboard shows:**  
> - Total revenue, profit, and margin by product / city / month  
> - Top 10 products and bottom 5 stores  
> - Monthly trend with slicers for category and location  

📄 **Export:** [Download PDF version][My dashboard Mexico.pdf][My dashboard Mexico (1).pdf](https://github.com/user-attachments/files/28190379/My.dashboard.Mexico.1.pdf)

   

*If you’d like to explore the interactive dashboard, I can share my screen or provide the `.pbix` file on request.*
