# Adolescent Fertility Trends: A Global Analysis (MA705 Project)

This repository contains the full workflow, data, analysis, and Quarto website for our MA705 (Regression) final project. Our study examines **global adolescent fertility rates** across countries, income groups, regions, and time, using data from the **World Bank**. We focus on descriptive statistics, regression modeling, and interactive data visualizations to understand patterns and disparities in fertility among girls aged 15–19 worldwide.

## Repository Structure

```
MA705-Project/
│
├── analysis.qmd # Main analysis page for the Quarto website
├── methods.qmd # Documentation of data retrieval, cleaning & enrichment
├── index.qmd # Main landing page for the website
│
├── df_clean.csv # Cleaned dataset used in analysis
├── project.ipynb # Notebook used for exploration, cleaning, tests, and plots
│
├── website/ # Auto-generated Quarto site files
│ ├── figs/ # Figures saved for use on the website
│ └── ... # Supporting site structure
│
├── requirements.txt # Python package requirements for full reproducibility
└── README.md # Project overview and reproduction instructions
```

---

# Project Overview

Our research explores three guiding questions:

1. **How are adolescent fertility rates distributed globally?**
2. **How do these rates vary across income groups and world regions?**
3. **How have adolescent fertility rates changed over time?**

The project includes:
- Meaningful **summary statistics** (mean, median, percentiles, variance)
- Regional and income-group analyses
- Trend analysis over time
- **Six+ visualizations** (histograms, boxplots, scatter plots, line charts, maps)
- At least **one interactive visualization** using Plotly
- A fully published **Quarto website** communicating our results

---

# Data Sources

We use publicly accessible data from the **World Bank Indicators API**:

- **Indicator:** Adolescent fertility rate (births per 1,000 girls aged 15–19)  
- **Additional data enrichment**: Region, income group, population log-transformation for visualization, etc.

Data files were retrieved, cleaned, merged, and validated following the standards described in `methods.qmd`.

---

# Data Cleaning & Enrichment Summary

Data processing steps (documented in `project.ipynb` and `methods.qmd`) include:

- Renaming columns for clarity  
- Handling missing values  
- Merging country metadata (region, income level)  
- Constructing a tidy dataset  
- Creating new variables (`pop_log`, `income_numeric`, etc.)  
- Verifying data quality (assertions on duplicates, missingness, row counts)

---

# Analysis Summary

The analysis includes:

### **Basic Summary Statistics**
- Distribution shape (strong right skew)
- Global mean, median, min, max, standard deviation
- Summary by **income group** and **region**
- Key observations motivating later modeling and visualization

### **Visualizations**
- Histogram of adolescent fertility  
- Boxplots by region and income group  
- Time trends for selected countries  
- Regional maps and choropleths  
- Interactive scatter plot with animation over time (Plotly)

### **Modeling**
- Linear regression modeling  
- Relationship between adolescent fertility and development indicators  
- Interpretation of regression coefficients and fit metrics  

All visualizations and tables appear on the Quarto website.

---

# Website (Quarto)

The full project website summarizes our analysis, methods, visuals, and conclusions.

To render the website locally:

```bash
quarto render
```

# Reproducibility Instructions

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd MA705-Project
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run analysis files

You can run either:

- `project.ipynb`  
- `analysis.qmd`

### 5. Render the Quarto website
```bash
quarto render
```

The output site will be generated in the `/website` folder.