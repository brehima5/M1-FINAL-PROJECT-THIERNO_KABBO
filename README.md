# Café Sales Data Analysis - Business Intelligence Report

## Project Overview

This project provides a comprehensive analysis of café sales data to help the café owner make data-driven decisions for marketing campaigns and operational improvements. We analyzed 10,000 transactions from 2023 to identify peak business periods, customer preferences, and revenue optimization opportunities. The analysis was conducted using both Python (Jupyter notebooks) and Excel to provide multiple perspectives on the data, focusing on when the busiest and most profitable times are, general sales trends, and data quality issues.

## Business Questions

Our analysis addressed the following key business questions:

1. **Analyze popular selling times**: 
   - When are the busiest AND most profitable times?
   - Are weekends busier than weekdays?

2. **Understand Customer Behavior**: What items do customers spend most on?

3. **Optimize Operations**: Which payment methods and locations drive the most revenue?

4. **Data Quality Assessment**: What issues exist in our transaction data?

5. **Product Performance**: Which products are the most profitable and top-selling?

6. **Customer Purchasing Patterns**: Do customers buy more "treat" items (like cake or cookies) during busy periods?

## Data Cleaning Summary

### Cleaning Process Overview
We implemented a systematic 2-step cleaning process:

1. **Standardization**: All blanks, errors, and unknown values were standardized as "UNKNOWN" 
2. **Imputation**: Missing values were handled using appropriate statistical methods based on data distribution

### Specific Cleaning Steps Performed

**Python Notebook Approach:**
- **Item Column**: Filled missing values with 'UNKNOWN' (969 unknown items identified)
- **Quantity Column**: Used median imputation (median = 3) for 479 missing values due to data skew
- **Price Per Unit**: Used mean imputation for 533 missing values (no significant skew detected)
- **Total Spent**: Recalculated using formula: Price Per Unit × Quantity (502 missing values resolved)
- **Transaction Date**: Dropped 460 rows with missing dates (final dataset: 9,540 transactions)
- **Payment Method & Location**: Left missing values as-is for analysis (31.78% and 39.61% missing respectively)

**Data Quality Issues Identified:**
- No duplicate transactions found
- Significant missing data in Payment Method (31.78%) and Location (39.61%) columns
- Some data inconsistencies in Total Spent calculations
- Date range: Complete year 2023 (January 1 - December 31)

## Key Findings

### Revenue Performance
- **Total Revenue**: $85,152.12 across 9,540 transactions
- **Average Transaction Value**: $8.93
- **Peak Revenue Month**: June ($7,409.88)
- **Top Revenue Day**: Sunday ($12,420.65)

### Product Analysis
**Top Products by Revenue:**
1. Salad: $16,186.84
2. Sandwich: $12,881.68  
3. Smoothie: $12,631.66
4. Juice: $10,042.20
5. Cake: $9,825.06

**Top Products by Quantity Sold:**
1. Coffee: 3,425 units
2. Juice: 3,351 units
3. Salad: 3,314 units
4. Cake: 3,278 units
5. Sandwich: 3,266 units

### Time-Based Insights
**Monthly Revenue Performance:**
- **Highest**: June ($7,409.88), October ($7,343.66), January ($7,249.60)
- **Lowest**: February ($6,667.20)

**Weekday vs Weekend Analysis:**
- **Weekdays**: $60,706.08 total revenue (6,802 transactions, $8.92 avg)
- **Weekends**: $24,446.04 total revenue (2,738 transactions, $8.93 avg)
- **Insight**: Weekdays generate significantly more total revenue due to higher transaction volume

**Daily Performance:**
- **Best Day**: Sunday ($12,420.65)
- **Worst Day**: Wednesday ($11,774.85)

### Customer Behavior Patterns
**Treat Items Analysis:**
- Weekday treat sales: 4,553 items (0.67 treats per transaction)
- Weekend treat sales: 1,818 items (0.66 treats per transaction)
- **Finding**: Treat consumption remains consistent regardless of busy periods

**Payment Method Preferences:**
- Digital Wallet: $19,681.58 (2,197 transactions, $8.96 avg)
- Cash: $19,600.30 (2,158 transactions, $9.08 avg)
- Credit Card: $19,453.40 (2,170 transactions, $8.96 avg)

**Location Performance:**
- In-store: $25,879.80 (2,872 transactions, $9.01 avg)
- Takeaway: $25,489.88 (2,889 transactions, $8.82 avg)

## Reflections

### Challenges Encountered
1. **Data Quality Issues**: Significant missing data in Payment Method and Location columns required careful handling
2. **Inconsistent Data Types**: Several columns needed type conversion and standardization
3. **Missing Value Strategy**: Required different imputation methods based on data distribution analysis
4. **Excel vs Python Coordination**: Ensuring consistency between Excel and Python analysis approaches

### Methodology Decisions
- Used median for Quantity imputation due to skewed distribution
- Used mean for Price Per Unit due to normal distribution
- Chose to drop Transaction Date missing values to maintain data integrity
- Preserved missing Payment Method and Location data for transparency in analysis


## Takeaways & Recommendations

### Strategic Recommendations

1. **Focus Marketing on Peak Times**
   - Target June, October, and January for major campaigns
   - Leverage Sunday traffic with special promotions
   - Consider weekday-specific strategies given higher transaction volume

2. **Product Portfolio Optimization**
   - **Promote High-Revenue Items**: Focus marketing on Salad and Sandwich offerings
   - **Leverage Popular Items**: Use Coffee and Juice as traffic drivers
   - **Treat Strategy**: Maintain consistent treat offerings as consumption patterns are stable

3. **Operational Improvements**
   - **Payment Systems**: All payment methods perform similarly - maintain current options
   - **Location Strategy**: In-store and Takeaway perform equally well - optimize both channels
   - **Data Collection**: Improve data capture for Payment Method and Location to reduce missing values

4. **Revenue Growth Opportunities**
   - **Weekend Strategy**: While weekends have fewer transactions, average values are similar - opportunity to increase weekend traffic
   - **Low-Performing Periods**: Develop targeted promotions for February and Wednesday to boost revenue

### Data Quality Recommendations
1. Implement better data validation at point of sale
2. Train staff on importance of complete transaction recording
3. Regular data quality audits to prevent future issues
4. Consider automated data validation rules
```
---

*This analysis was conducted using both Python (pandas, matplotlib, and seaborn) and Excel to provide comprehensive insights for business decision-making. The dual-approach ensures accessibility for stakeholders with different technical backgrounds.*
