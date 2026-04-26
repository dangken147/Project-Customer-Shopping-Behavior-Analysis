# Data Dictionary - Customer Shopping Behavior Dataset

## Overview
**Dataset Name:** customer_shopping_behavior  
**Total Records:** 3,900 transactions  
**Total Attributes:** 18 columns  
**Data Types:** 4 numeric, 13 categorical  
**Missing Values:** 37 (0.95%) in Review Rating column  

---

## Column Definitions

### 1. **Customer ID** 
- **Data Type:** Integer (INT)
- **Range:** 1 - 3,900
- **Uniqueness:** Unique identifier for each customer
- **Business Meaning:** Primary key for identifying individual customers
- **Example Values:** 1, 2, 3, ..., 3900
- **Notes:** One row per transaction; customers may have multiple rows if they made repeat purchases

---

### 2. **Age**
- **Data Type:** Integer (INT)
- **Range:** 18 - 70 years
- **Distribution:** Mean = 44.07, Std Dev = 15.21, Median = 44
- **Business Meaning:** Customer age at time of purchase; used for demographic segmentation
- **Example Values:** 18, 25, 35, 44, 55, 70
- **Valid Range:** Adults only (18+); no minors in dataset
- **Notes:** No null values; uniformly distributed across age groups

---

### 3. **Gender**
- **Data Type:** String/Categorical
- **Valid Values:** "Male", "Female"
- **Unique Values:** 2
- **Distribution:** Male = 68% (2,652), Female = 32% (1,248)
- **Business Meaning:** Customer gender for targeted marketing and product preference analysis
- **Example Values:** Male, Female
- **Notes:** No null values; male-skewed customer base

---

### 4. **Item Purchased**
- **Data Type:** String/Categorical
- **Valid Values:** 25 unique product names (see list below)
- **Examples:** Blouse, Sweater, Jeans, Sandals, T-Shirt, Shorts, Jacket, etc.
- **Business Meaning:** Specific product name purchased
- **Distribution:** Blouse is most popular (171 purchases), others vary
- **Notes:** Spans across 4 product categories (Clothing, Footwear, Electronics, Home)

**Product List (25 items):**
Blouse, Sweater, Jeans, Sandals, T-Shirt, Shorts, Jacket, Dress, Scarf, Hat, Boots, Heels, Socks, Backpack, Wallet, Watch, Ring, Necklace, Bracelet, Earrings, Lamp, Chair, Table, Sofa, Desk

---

### 5. **Category**
- **Data Type:** String/Categorical
- **Valid Values:** "Clothing", "Footwear", "Electronics", "Home"
- **Unique Values:** 4 major product categories
- **Distribution:** 
  - Clothing: 44.5% (1,737)
  - Footwear: ~15% (584)
  - Electronics: ~20% (780)
  - Home: ~20% (799)
- **Business Meaning:** Product category for category-level analysis and inventory management
- **Notes:** Hierarchical relationship with Item Purchased (many items per category)

---

### 6. **Purchase Amount (USD)**
- **Data Type:** Numeric/Integer (INT)
- **Range:** $20 - $100
- **Distribution:** Mean = $59.76, Std Dev = $23.69, Median = $60
- **Percentiles:** 25th = $39, 50th = $60, 75th = $81
- **Business Meaning:** Transaction value in US dollars; primary revenue metric
- **Example Values:** 20, 39, 53, 60, 73, 90, 100
- **Currency:** USD (United States Dollar)
- **Notes:** No missing values; appears evenly distributed; no outliers

---

### 7. **Location**
- **Data Type:** String/Categorical
- **Valid Values:** 50 US state names
- **Unique Values:** 50 states
- **Distribution:** Montana leads (96 transactions), fairly balanced across states
- **Business Meaning:** Geographic location of customer; used for regional analysis and logistics
- **Example Values:** Kentucky, Maine, Massachusetts, Montana, California, Texas, etc.
- **Geographic Scope:** All 50 US states represented
- **Notes:** No international locations; data is US-only

---

### 8. **Size**
- **Data Type:** String/Categorical
- **Valid Values:** "S", "M", "L", "XL"
- **Unique Values:** 4 clothing sizes
- **Distribution:** M = 44.9% (1,755), S, L, XL roughly equal
- **Business Meaning:** Product size for clothing items; inventory management
- **Applicable To:** Clothing and Footwear categories primarily
- **Example Values:** S, M, L, XL
- **Notes:** Not all products have size relevance (e.g., Lamps, Watches); standard apparel sizing

---

### 9. **Color**
- **Data Type:** String/Categorical
- **Valid Values:** 25 unique color names
- **Unique Values:** 25 distinct colors
- **Distribution:** Olive is most popular (177 purchases), others vary
- **Business Meaning:** Product color for design preference analysis and inventory
- **Example Values:** Gray, Maroon, Turquoise, Olive, Blue, Red, Black, White, Green, etc.
- **Notes:** Large variety suggests diverse customer color preferences

**Color List (25):**
Olive, Gray, Maroon, Turquoise, Blue, Red, Black, White, Green, Yellow, Pink, Purple, Orange, Brown, Beige, Navy, Teal, Lime, Coral, Gold, Silver, Khaki, Charcoal, Crimson, Indigo

---

### 10. **Season**
- **Data Type:** String/Categorical
- **Valid Values:** "Winter", "Spring", "Summer", "Fall"
- **Unique Values:** 4 seasons
- **Distribution:** Spring = 25.6% (999), others roughly balanced
- **Business Meaning:** Time of year for seasonal demand analysis and campaign planning
- **Example Values:** Winter, Spring, Summer, Fall
- **Notes:** Used for seasonal trend analysis; Spring shows highest transaction volume

---

### 11. **Review Rating**
- **Data Type:** Numeric/Float (DECIMAL)
- **Range:** 2.5 - 5.0 (out of 5.0)
- **Valid Values:** Rating on 5-point Likert scale
- **Distribution:** Mean = 3.75, Std Dev = 0.72, Median = 3.8
- **Missing Values:** 37 nulls (0.95% of 3,900 records)
- **Imputation Strategy:** Filled with category-wise median to preserve distribution
- **Business Meaning:** Customer satisfaction score; quality indicator for product/service
- **Example Values:** 2.5, 3.1, 3.5, 3.8, 4.4, 5.0
- **Notes:** 
  - Post-imputation: 0 missing values
  - Median imputation grouped by Category (Clothing, Footwear, Electronics, Home)
  - Ratings skew slightly positive (mean > median)

---

### 12. **Subscription Status**
- **Data Type:** String/Categorical
- **Valid Values:** "Yes", "No"
- **Unique Values:** 2
- **Distribution:** No = 72.9% (2,847), Yes = 27.1% (1,053)
- **Business Meaning:** Whether customer has active subscription; recurring revenue indicator
- **Example Values:** Yes, No
- **Notes:** 27% subscription rate; opportunity for growth

---

### 13. **Shipping Type**
- **Data Type:** String/Categorical
- **Valid Values:** 6 shipping methods (see list below)
- **Unique Values:** 6
- **Distribution:** Free Shipping = 17.3% (675), Express = varied
- **Business Meaning:** Fulfillment method; affects margins and delivery time
- **Example Values:** Express, Free Shipping, Standard, Next Day Air, Priority, Regular
- **Notes:** Free Shipping is most popular option (cost incentive)

**Shipping Methods (6):**
- Standard Shipping
- Express Shipping
- Free Shipping
- Next Day Air
- Priority Mail
- Regular Delivery

---

### 14. **Discount Applied**
- **Data Type:** String/Categorical
- **Valid Values:** "Yes", "No"
- **Unique Values:** 2
- **Distribution:** No = 57% (2,223), Yes = 43% (1,677)
- **Business Meaning:** Whether promotional discount was applied; promotional effectiveness metric
- **Example Values:** Yes, No
- **Notes:** 43% of purchases include discounts; significant discount penetration

---

### 15. **Promo Code Used**
- **Data Type:** String/Categorical
- **Valid Values:** "Yes", "No"
- **Unique Values:** 2
- **Distribution:** No = 57% (2,223), Yes = 43% (1,677)
- **Business Meaning:** Whether customer used promotional code; marketing campaign effectiveness
- **Example Values:** Yes, No
- **Correlation:** Highly correlated with Discount Applied (same distribution)
- **Notes:** 43% promo code usage; suggests strong promotional campaigns

---

### 16. **Previous Purchases**
- **Data Type:** Integer (INT)
- **Range:** 1 - 50
- **Distribution:** Mean = 25.35, Std Dev = 14.45, Median = 25
- **Percentiles:** 25th = 13, 50th = 25, 75th = 38
- **Business Meaning:** Customer lifetime purchase history (prior to this transaction); loyalty indicator
- **Example Values:** 1 (new), 5, 14, 25, 31, 49, 50 (most loyal)
- **Segmentation:**
  - New: 1 previous purchase
  - Returning: 2-10 previous purchases
  - Loyal: 11+ previous purchases
- **Notes:** Wide range indicates diverse customer maturity; median = 25 suggests typical repeat customer

---

### 17. **Payment Method**
- **Data Type:** String/Categorical
- **Valid Values:** 6 payment methods (see list below)
- **Unique Values:** 6
- **Distribution:** PayPal = 17.4% (677), Credit Card, Cash, Venmo, Apple Pay, Google Pay
- **Business Meaning:** Payment instrument; affects fraud risk, chargebacks, and processing fees
- **Example Values:** Credit Card, PayPal, Venmo, Cash, Apple Pay, Google Pay
- **Notes:** PayPal most popular (digital payment trend); credit card second

**Payment Methods (6):**
1. Credit Card
2. PayPal
3. Venmo
4. Cash
5. Apple Pay
6. Google Pay

---

### 18. **Frequency of Purchases**
- **Data Type:** String/Categorical
- **Valid Values:** 7 purchase frequency levels (see list below)
- **Unique Values:** 7
- **Distribution:** Every 3 Months = 14.9% (584), Weekly, Monthly, Fortnightly, etc.
- **Business Meaning:** Purchase cadence; indicates customer loyalty and lifetime value potential
- **Example Values:** Weekly, Fortnightly, Monthly, Every 3 Months, Semi-Annually, Annually, On-Demand
- **Notes:** Diverse purchase patterns; suggests varied customer segments

**Frequency Levels (7):**
1. Weekly - High frequency, repeat buyer
2. Fortnightly (Every 2 weeks) - Regular buyer
3. Monthly - Standard frequency
4. Every 3 Months - Quarterly
5. Semi-Annually (Every 6 months) - Occasional
6. Annually (Once per year) - Infrequent
7. On-Demand - Sporadic/irregular purchases

---

## Data Quality Summary

| Metric | Value |
|--------|-------|
| **Total Records** | 3,900 |
| **Total Columns** | 18 |
| **Missing Values** | 37 (0.95% - Review Rating only) |
| **Duplicate Records** | 0 |
| **Data Completeness** | 99.05% |
| **Date Range** | N/A (single period snapshot) |
| **Last Updated** | 2026-04-26 |

---

## Data Types Summary

| Data Type | Count | Columns |
|-----------|-------|----------|
| Integer (INT) | 4 | Customer ID, Age, Purchase Amount, Previous Purchases |
| Float (NUMERIC) | 1 | Review Rating |
| String (VARCHAR) | 13 | Gender, Item Purchased, Category, Location, Size, Color, Season, Subscription Status, Shipping Type, Discount Applied, Promo Code Used, Payment Method, Frequency of Purchases |
| **TOTAL** | **18** | |

---

## Statistical Summary

### Numeric Columns

| Column | Count | Mean | Std Dev | Min | 25% | 50% | 75% | Max |
|--------|-------|------|---------|-----|-----|-----|-----|-----|
| Age | 3,900 | 44.07 | 15.21 | 18 | 31 | 44 | 57 | 70 |
| Purchase Amount | 3,900 | 59.76 | 23.69 | 20 | 39 | 60 | 81 | 100 |
| Previous Purchases | 3,900 | 25.35 | 14.45 | 1 | 13 | 25 | 38 | 50 |
| Review Rating | 3,863* | 3.75 | 0.72 | 2.5 | 3.1 | 3.8 | 4.4 | 5.0 |

*Note: Review Rating has 37 missing values; statistics calculated on 3,863 non-null records

---

## Usage Notes

1. **For Analysis:** Use `data/processed/customer_cleaned.csv` (with Review Rating imputed)
2. **For Raw Data:** Use `data/raw/customer_shopping_behavior.csv` (with 37 nulls)
3. **Geographic Focus:** US-only dataset; 50 states represented
4. **Time Period:** Single period snapshot; no time-series data
5. **Currency:** All monetary values in USD ($)
6. **Imputation Method:** Review Rating filled with category-wise median (preserves distribution)

---

## Contact

For questions about the dataset, contact: dangken147

---

**Last Updated:** 2026-04-26  
**Version:** 1.0
