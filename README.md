# Sales Data Cleaning & Business Analysis

## 1. Project Overview

This project performs data cleaning, validation, exploratory analysis, and business analysis on a Superstore sales dataset.

The objective is to transform raw sales data into a clean and reliable dataset and generate business insights related to sales, profitability, products, categories, discounts, and regional performance.

---

## 2. Business Objectives

The analysis aims to:

- Clean and validate the raw sales dataset.
- Identify missing values and duplicate records.
- Validate data types and numerical values.
- Identify inconsistencies in product information.
- Analyze overall sales and profitability.
- Compare product category and sub-category performance.
- Investigate the relationship between discounts and profitability.
- Identify loss-making products.
- Analyze regional performance.
- Provide actionable business recommendations.

---

## 3. Dataset

The project uses the Superstore sales dataset containing transaction-level information such as:

- Order ID
- Order Date
- Ship Date
- Ship Mode
- Customer ID
- Customer Name
- Segment
- Country/Region
- City
- State/Province
- Postal Code
- Region
- Product ID
- Category
- Sub-Category
- Product Name
- Sales
- Quantity
- Discount
- Profit

The raw dataset contains **10,194 transaction records and 21 columns**.

---

## 4. Data Cleaning & Validation

The following data-quality checks were performed:

- Dataset dimensions and column inspection
- Data type validation
- Missing-value detection
- Duplicate-row detection
- Duplicate Row ID detection
- Duplicate Order ID analysis
- Date consistency validation
- Discount range validation
- Quantity validation
- Sales validation
- Negative-profit identification
- Customer ID and Customer Name consistency
- Product ID and Product Name consistency
- Product category consistency
- Product sub-category consistency
- Text formatting and column-name standardization

### Key Data Quality Results

- Missing values: **0**
- Duplicate rows: **0**
- Duplicate Row IDs: **0**
- Invalid shipment dates: **0**
- Invalid discount values: **0**
- Invalid quantity values: **0**
- Zero-sales records: **0**

A product-name consistency issue was identified involving **32 Product IDs linked to multiple product names**. This was investigated separately rather than blindly modifying the original product information.

---

## 5. Key Performance Indicators

| Metric | Value |
|---|---:|
| Total Sales | USD 2.33 million |
| Total Profit | USD 292,296.81 |
| Profit Margin | 12.56% |
| Total Quantity Sold | 38,654 |
| Unique Orders | 5,111 |
| Unique Customers | 804 |
| Unique Products | 1,862 |
| Average Sales per Order | USD 455.20 |

---

## 6. Category Performance

Technology generated the highest total profit among the three product categories.

Office Supplies also generated strong profitability, while Furniture generated substantially lower profit compared with Technology and Office Supplies.

### Most Profitable Category

**Technology**

Profit: approximately **USD 146,543**

This indicates that Technology is the strongest contributor to overall profitability.

---

## 7. Sub-Category Performance

### Most Profitable Sub-Category

**Copiers**

- Profit: approximately **USD 55,694**
- Profit margin: approximately **37.21%**

### Least Profitable Sub-Category

**Tables**

- Profit: approximately **-USD 17,753**
- Profit margin: approximately **-8.53%**

Tables represent the most significant profitability concern in the dataset.

---

## 8. Table Profitability Investigation

Because Tables were the least profitable sub-category, additional analysis was performed.

The average discount for Tables was approximately **25.81%**, compared with an overall dataset average of approximately **15.54%**.

### Discount Analysis

| Discount | Profit |
|---:|---:|
| 0% | USD 13,335 |
| 20% | approximately -USD 299 |
| 30% | approximately -USD 3,493 |
| 40% | approximately -USD 16,188 |
| 45% | approximately -USD 2,493 |
| 50% | approximately -USD 8,615 |

Table transactions without discounts generated approximately **USD 13,335 in profit**, while discounted Table transactions collectively generated a loss of approximately **USD 31,088**.

This indicates a strong association between higher discount levels and poor Table profitability. However, the analysis does not establish that discounting alone caused the losses.

---

## 9. Product Concentration

The 10 worst-performing Table products accounted for approximately **68.81% of the total loss within the Tables sub-category**.

This indicates that the losses are concentrated among a relatively small number of products rather than being evenly distributed across all Table products.

This concentration provides an opportunity for targeted corrective action.

---

## 10. Regional Performance

The regional analysis showed significant differences in Table profitability.

### Worst Region

**East**

- Table loss: approximately **USD 11,086**
- Average Table discount: approximately **35.88%**

### Best Region

**West**

The West was the only region that generated a positive profit from Tables.

The results suggest that regional pricing and discount strategies may be contributing to differences in profitability.

---

## 11. East Region Product Concentration

The 10 worst-performing Table products in the East accounted for approximately **57.70% of the East region's total Table loss**.

This further demonstrates that the problem is concentrated among a relatively small number of products and can potentially be addressed through targeted product-level actions.

---

## 12. Business Recommendations

Based on the analysis, the following actions are recommended:

1. Review discount policies for Table products, particularly high-discount transactions.
2. Investigate the highest-loss Table products individually before continuing aggressive discounting.
3. Review Table pricing and discount strategy in the East region.
4. Consider reducing or restructuring discounts that consistently produce negative margins.
5. Investigate whether the highest-loss products should be repriced, promoted differently, replaced, or discontinued.
6. Continue monitoring Technology products because the category currently generates the strongest profitability.
7. Use product-level and regional profitability rather than sales volume alone when making pricing decisions.

---

## 13. Visualizations

The project includes visualizations covering:

- Monthly sales trend
- Monthly profit trend
- Sales by product category
- Profit by product category
- Profit by sub-category
- Table profit by discount level
- Table profit by region
- Worst Table product profitability by discount level

All visualizations are stored in the `images/` directory.

---

## 14. Project Structure

```text
Sales-Data-Cleaning-Analysis/
│
├── data/
│   ├── sample_-_superstore.xls
│   ├── superstore_cleaned.csv
│   ├── final_kpi_summary.csv
│   ├── category_performance.csv
│   ├── subcategory_performance.csv
│   └── business_findings.csv
│
├── images/
│   ├── monthly_profit_trend.png
│   ├── monthly_sales_trend.png
│   ├── profit_by_category.png
│   ├── profit_by_subcategory.png
│   ├── sales_by_category.png
│   ├── tables_profit_by_discount.png
│   ├── tables_profit_by_region.png
│   └── worst_table_product_profit_by_discount.png
│
├── notebook/
│   └── sales_data_cleaning_analysis.ipynb
│
└── README.md