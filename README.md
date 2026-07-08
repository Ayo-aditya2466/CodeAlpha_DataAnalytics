# 💎 Diamond Pricing: Exploratory Data Analysis & Visualization

**CodeAlpha Data Analytics Internship — Task 2 (EDA) & Task 3 (Data Visualization)**

An end-to-end exploratory data analysis of a 54,000-row real-world diamond pricing dataset, uncovering
what actually drives diamond prices, exposing a classic confounding-variable trap in the raw data, and
communicating findings through a set of clean, professional visualizations.

---

## 📊 Project Overview

This project answers five business questions about diamond pricing:

1. What does the price distribution look like, and is it symmetric?
2. Which attribute drives price the most — carat or the "4Cs" (cut, color, clarity)?
3. Do higher quality grades always mean a higher price?
4. What data quality issues exist, and how do they affect analysis?
5. What's the actionable takeaway for a jewelry business?

The standout finding: **raw averages showed Fair-cut diamonds priced higher than Ideal-cut diamonds** —
a counter-intuitive result caused by carat weight confounding the comparison. Controlling for carat
(price-per-carat) reveals the expected, real effect of cut quality. This is documented step-by-step in
the notebook as a demonstration of rigorous — not surface-level — analysis.

## 🗂 Folder Structure

```
CodeAlpha_DataAnalytics/
├── data/
│   └── diamonds.csv              # Raw dataset (53,940 rows, 10 columns)
├── notebook/
│   └── diamond_price_analysis.ipynb   # Full analysis: cleaning, EDA, visualization, insights
├── images/
│   └── *.png                     # Exported charts (also embedded in the notebook)
├── requirements.txt
└── README.md
```

## 📁 Dataset

- **Source:** [`mwaskom/seaborn-data`](https://github.com/mwaskom/seaborn-data) (public GitHub repository)
- **Size:** 53,940 rows × 10 columns
- **Fields:** `carat`, `cut`, `color`, `clarity`, `depth`, `table`, `price`, `x`, `y`, `z`

## 🧹 Data Cleaning Performed

- Checked for and confirmed no missing values
- Removed **146 duplicate rows**
- Removed rows with **impossible 0mm physical dimensions** (data-entry errors)
- Removed extreme outliers in dimension fields inconsistent with any real diamond

## 📈 Key Visualizations

| Chart | Insight |
|---|---|
| Price distribution (raw + log) | Prices are strongly right-skewed |
| Correlation heatmap | Carat correlates with price at ~0.92 |
| Carat vs. price scatter | Relationship is non-linear / exponential |
| Price by cut/color/clarity (boxplots) | Raw averages are confounded by carat |
| Price-per-carat by cut (bar chart) | The *true*, carat-controlled effect of cut quality |
| Carat vs. price faceted by clarity | Clarity's price premium grows with diamond size |
| Market composition | Distribution of diamonds across grade categories |

## 🛠 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/Ayo-aditya2466/CodeAlpha_DataAnalytics.git
cd CodeAlpha_DataAnalytics

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch Jupyter and run the notebook top to bottom
jupyter notebook notebook/diamond_price_analysis.ipynb
```

## 🔍 Key Findings

1. **Carat is the dominant price driver** and its relationship with price is non-linear.
2. **Raw quality-grade averages can be misleading** without controlling for carat — a real
   confounding-variable trap, resolved using price-per-carat analysis.
3. **Data cleaning materially changes results** — duplicates and impossible measurements were
   present and removed before any conclusions were drawn.
4. Clarity's price premium is more pronounced in larger diamonds.

## 🚀 Future Improvements

- Build a regression model (on `log(price)`) to quantify each feature's exact contribution
- Incorporate certification/brand data if available, to explain remaining price variance
- Deploy an interactive dashboard (e.g. Streamlit/Plotly Dash) for live filtering by grade

## 🧰 Tools Used

Python · Pandas · NumPy · Matplotlib · Seaborn · SciPy · Jupyter Notebook

---

*Built as part of the [CodeAlpha](https://www.codealpha.tech) Data Analytics Internship.*
