# Customer Shopping Behavior Analysis

## 📋 Project Overview

This project analyzes **3,900+ customer transactions** to identify shopping patterns, customer segments, and business opportunities. Using **Python (Pandas, Matplotlib, Seaborn)**, **SQL**, and **Power BI**, we deliver actionable insights for marketing and business strategy.

**Dataset:** 3,900 transactions × 18 attributes  
**Time Period:** Multi-season analysis (Winter, Spring, Summer, Fall)  
**Geographic Scope:** 50 US states  

---

## 🎯 Key Business Questions Answered

| # | Question | Insight |
|---|----------|----------|
| Q1 | Revenue by Gender | Compare male vs. female customer spending |
| Q2 | High-Value Discounted Purchases | Identify discount-sensitive high-spenders |
| Q3 | Top 5 Products by Rating | Best-rated items for recommendation |
| Q4 | Shipping Type Impact | Standard vs. Express shipping ROI |
| Q5 | Subscription Value | Do subscribers spend more? |
| Q6 | Discount Product Affinity | Which products have highest discount rates |
| Q7 | Customer Segmentation | New vs. Returning vs. Loyal customers |
| Q8 | Category Winners | Top 3 products per category |
| Q9 | Repeat Buyer Subscription | Correlation between loyalty & subscription |
| Q10 | Age Group Revenue | Which age groups generate most revenue |

---

## 📊 Data Pipeline

```
┌─────────────────────────────────────────────────────────────┐
│                  RAW DATA SOURCE                            │
│        customer_shopping_behavior.csv (3,900 rows)         │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│                DATA CLEANING & VALIDATION                  │
│  - Handle missing values (Review Rating: 37 nulls → median)│
│  - Type conversion & normalization                         │
│  - Outlier detection & handling                            │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│              EXPLORATORY DATA ANALYSIS (EDA)              │
│  - Descriptive statistics (mean, std, distribution)       │
│  - Correlation analysis & relationships                   │
│  - Visualization (Matplotlib, Seaborn)                    │
└─────────────────┬───────────────────────────────────────────┘
                  │
         ┌────────┴────────┐
         ▼                 ▼
   ┌──────────────┐  ┌──────────────┐
   │ SQL Queries  │  │ Python Stats │
   │ (10 Q's)     │  │ Analysis     │
   └──────────────┘  └──────────────┘
         │                 │
         └────────┬────────┘
                  ▼
┌─────────────────────────────────────────────────────────────┐
│           VISUALIZATION & DASHBOARDING                     │
│  - Power BI (Customer-Shopping-Behavior.pbix)             │
│  - Matplotlib/Seaborn charts in Jupyter                   │
└─────────────────┬───────────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────────┐
│         BUSINESS INSIGHTS & RECOMMENDATIONS               │
│         (Customer_Growth_Strategy.pptx)                    │
└─────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| **Python 3.8+** | Data processing & analysis |
| **Pandas** | Data manipulation & cleaning |
| **NumPy** | Numerical computations |
| **Matplotlib & Seaborn** | Data visualization |
| **Scikit-learn** | Machine learning & preprocessing |
| **Jupyter Notebook** | Interactive analysis & documentation |
| **SQL (PostgreSQL/MySQL)** | Database queries & aggregations |
| **Power BI** | Business intelligence dashboards |

---

## 📁 Project Structure

```
Project-Customer-Shopping-Behavior-Analysis/
├── README.md                          # Project overview (you are here)
├── requirements.txt                   # Python dependencies
├── .gitignore                         # Git configuration
│
├── data/
│   ├── raw/
│   │   ├── customer_shopping_behavior.csv    # Original dataset
│   │   └── .gitkeep
│   └── processed/
│       ├── customer_cleaned.csv              # Cleaned data
│       └── .gitkeep
│
├── notebooks/
│   ├── Customer_Shopping_Behavior_Analysis.ipynb  # Main analysis
│   └── .gitkeep
│
├── sql/
│   ├── customer_behavior_sql_queries.sql    # 10 analytical queries
│   └── .gitkeep
│
├── dashboards/
│   ├── Customer-Shopping-Behavior.pbix      # Power BI dashboard
│   └── .gitkeep
│
└── docs/
    ├── DATA_DICTIONARY.md                   # Column definitions
    ├── Business Problem Document.pdf         # Requirements
    ├── Business Problem Document Vietnamese ver.pdf
    ├── Customer Shopping Behavior Analysis.docx
    ├── Customer Shopping Behavior Analysis Vietnamese ver.docx
    ├── Customer_Growth_Strategy.pptx        # Presentation
    └── .gitkeep
```

---

## 🚀 Quick Start

### 1. **Clone Repository**
```bash
git clone https://github.com/dangken147/Project-Customer-Shopping-Behavior-Analysis.git
cd Project-Customer-Shopping-Behavior-Analysis
```

### 2. **Set Up Environment**
```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 3. **Run Analysis**
```bash
# Launch Jupyter
jupyter notebook

# Open: notebooks/Customer_Shopping_Behavior_Analysis.ipynb
```

---

## 📊 Dataset Features (18 Attributes)

| Column | Type | Description |
|--------|------|-------------|
| **Customer ID** | int | Unique customer identifier (1-3900) |
| **Age** | int | Customer age (18-70 years) |
| **Gender** | string | Male / Female |
| **Item Purchased** | string | Product name (25 unique items) |
| **Category** | string | Product category (4: Clothing, Footwear, Electronics, Home) |
| **Purchase Amount (USD)** | int | Transaction value ($20-$100) |
| **Location** | string | US state (50 states) |
| **Size** | string | Product size (S, M, L, XL) |
| **Color** | string | Product color (25 unique colors) |
| **Season** | string | Purchase season (Winter, Spring, Summer, Fall) |
| **Review Rating** | float | Customer rating (2.5-5.0, 37 missing → median imputed) |
| **Subscription Status** | string | Yes / No |
| **Shipping Type** | string | Standard / Express / Free Shipping / Next Day Air (6 types) |
| **Discount Applied** | string | Yes / No |
| **Promo Code Used** | string | Yes / No |
| **Previous Purchases** | int | Number of past purchases (1-50) |
| **Payment Method** | string | Credit Card / PayPal / Venmo / Cash (6 methods) |
| **Frequency of Purchases** | string | Weekly / Fortnightly / Monthly / etc. (7 frequencies) |

---

## 💡 Key Findings (Preliminary)

✅ **Data Quality:**
- ✓ Complete dataset: 3,900 rows, 0.95% missing (Review Rating only)
- ✓ No duplicates detected
- ✓ Age range: 18-70 (median: 44)
- ✓ Purchase amount: $20-$100 (median: $60)

✅ **Customer Insights:**
- Male customers: 68% of dataset (2,652 / 3,900)
- Subscription adoption: 27% (1,053 subscribers)
- Most popular payment: PayPal (677 transactions)
- Discount penetration: 57% of purchases include discounts

✅ **Product Insights:**
- Top category: Clothing (1,737 purchases / 44.5%)
- 25 unique products across 4 categories
- Rating average: 3.75 / 5.0 (std: 0.72)

---

## 📈 Analysis Highlights

### SQL Queries Implemented
1. **Revenue by Gender** - Segment spending by demographics
2. **Discount Efficiency** - High-value discounted purchases
3. **Product Rankings** - Top performers by rating
4. **Shipping ROI** - Cost-benefit of shipping types
5. **Subscription Value** - Impact on revenue & frequency
6. **Discount Affinity** - Which products drive promotional sales
7. **Customer Lifecycle** - Segment by loyalty stage
8. **Category Leaders** - Best products per category
9. **Repeat Buyer Behavior** - Loyalty & subscription correlation
10. **Age Group Segmentation** - Demographic revenue contribution

### Python Analysis (Jupyter)
- Descriptive statistics & distributions
- Missing value analysis & imputation strategy
- Correlation matrices & feature relationships
- Customer segmentation (RFM analysis ready)
- Visualizations: histograms, heatmaps, bar charts

### Power BI Dashboard
- Interactive filters (Gender, Location, Subscription, etc.)
- KPI cards (Total Revenue, Avg Order Value, etc.)
- Trend analysis (seasonal patterns)
- Heatmaps (product performance by region)

---

## 🎓 Learning Outcomes

This project demonstrates:

1. **Data Engineering**: Loading, cleaning, validating, and transforming raw data at scale
2. **SQL Mastery**: Complex queries (CTEs, window functions, aggregations, case statements)
3. **Statistical Analysis**: Descriptive stats, distributions, correlations, segmentation
4. **Business Analytics**: Translating data into actionable business recommendations
5. **Visualization & Communication**: Presenting insights via dashboards, charts, and reports

---

## 🔧 Development Workflow

### Setup New Environment
```bash
./scripts/setup_project.py  # (Creates folder structure, installs deps)
```

### Adding New Analysis
1. Create new notebook in `notebooks/`
2. Add queries to `sql/` if database queries needed
3. Export visualizations to `dashboards/`
4. Document findings in this README

### Deploying Changes
```bash
git add .
git commit -m "analysis: [description]"
git push origin feature/[feature-name]
```

---

## 📞 Contact & Support

**Author:** dangken147  
**Repository:** https://github.com/dangken147/Project-Customer-Shopping-Behavior-Analysis  
**Last Updated:** 2026-04-26  

---

## 📝 License

This project is open-source for educational purposes.

---

**Next Steps:**
- [ ] Run `setup_project.py` to organize folder structure
- [ ] Execute Jupyter notebook for full analysis
- [ ] Open Power BI dashboard for interactive exploration
- [ ] Review SQL queries against live database
- [ ] Present insights to stakeholders
