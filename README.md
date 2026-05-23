# 🎮 PixelZone Gaming Café — Big Data Analytics

> End-to-end Big Data Analytics project: synthetic dataset generation, Python visualizations, and ML-based revenue forecasting for a gaming café concept in Kuala Lumpur, Malaysia.

---

## Project Overview

This project applies Big Data Analytics principles to a real-world business scenario — **PixelZone Gaming Café**, a fictional high-end gaming and entertainment centre in Kuala Lumpur. The full pipeline covers dataset design, exploratory visualization, machine learning regression, and evidence-based business decision-making.

**Module:** IBM4208 – Big Data Analytics | INTI International University (Jan 2026)

---

## Key Results

| Model | MAE (MYR) | RMSE (MYR) | R² Score |
|-------|-----------|------------|----------|
| Linear Regression | 85.75 | 111.86 | **0.9838** ✅ |
| Random Forest | 328.37 | 404.73 | 0.7880 |

> Linear Regression achieved **98.4% accuracy** on monthly revenue prediction, outperforming Random Forest due to the dataset's consistently linear growth trend.

**2026 Revenue Forecast:** MYR ~174,300 (+2.1% over 2025)

---

## Repository Structure

```
pixelzone-big-data-analytics/
│
├── notebooks/
│   └── PixelZone_BigData_Analytics.ipynb   # Full pipeline notebook
│
├── data/
│   └── pixelzone_dataset.csv               # Generated dataset (50,000 rows)
│
├── outputs/
│   └── charts/
│       ├── chart1_monthly_revenue.png
│       ├── chart2_genre_popularity.png
│       ├── chart3_ratings.png
│       ├── chart4_residual_analysis.png
│       ├── chart5_actual_vs_predicted.png
│       └── chart6_forecast_2026.png
│
└── README.md
```

---

## What's Inside the Notebook

The notebook is organized into 5 self-contained parts:

### Part 1 — Dataset Generation
Synthetically generates 50,000 customer session records spanning Jan 2021 – Dec 2025 with embedded business-realistic patterns:
- Peak demand weighted toward **6PM–2AM** and weekends
- **~5% year-on-year revenue growth** via hourly rate multipliers
- Membership-tiered pricing: Basic / Silver / Gold across Casual and VIP zones
- Seasonal food combo distributions (holiday months: June, July, December)
- Age distribution centred on 21 (core student demographic)

**Dataset schema — 16 columns:**

| Column | Type | Description |
|--------|------|-------------|
| Session_ID | String | Unique session identifier |
| Date | Date | Session date (2021–2025) |
| Day_of_Week | String | Day name |
| Time_Period | String | Time slot (e.g. 10PM–2AM) |
| Customer_ID | String | Customer identifier |
| Age | Integer | Customer age |
| Membership_Type | String | Basic / Silver / Gold |
| Zone | String | Casual or VIP |
| Game_Genre | String | FPS / RPG / Sports / Strategy / Racing / VR |
| Hours_Played | Float | Session duration (hours) |
| Hourly_Rate_MYR | Float | Rate per hour (MYR) |
| Total_Amount_MYR | Float | Total session revenue |
| Payment_Method | String | Cash / Card / E-Wallet |
| Food_Combo | String | Food package ordered |
| Rating | Integer | Customer satisfaction (1–5) |
| Repeat_Customer | String | Yes / No |

### Part 2 — Data Validation & Export
Validates data quality (zero null values, realistic ranges, correct distributions) and exports the dataset as CSV.

### Part 3 — Python Visualizations
Three business-insight charts using `matplotlib` and `seaborn`:
- **Monthly Revenue Trend** — steady year-on-year growth with mid-year dips
- **Game Genre Popularity** — near-uniform distribution across all 6 genres
- **Customer Ratings Distribution** — 62.1% positive (4–5 star) ratings

### Part 4 — Machine Learning Regression
- Aggregates 50,000 session records into 60 monthly summaries
- 80/20 train-test split (48 months training, 12 months testing)
- Compares Linear Regression vs Random Forest across MAE, RMSE, and R²
- Includes residual analysis to validate model reliability

### Part 5 — 2026 Revenue Forecast
Projects monthly revenue for all 12 months of 2026 using the best-performing Linear Regression model, assuming 5% session growth and proportional rate increases.

---

## Big Data Characteristics (5Vs)

| V | How it applies to PixelZone |
|---|----------------------------|
| **Volume** | 50,000 session records across 16 columns; scales to millions in multi-branch operations |
| **Velocity** | Data generated continuously at check-in, mid-session, and checkout touchpoints |
| **Variety** | Mix of integer, float, string, and datetime data types |
| **Veracity** | Constrained categorical values, realistic numerical ranges, zero null values |
| **Value** | Revenue forecasting, dynamic pricing, loyalty analysis, staffing optimization |

---

## Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data manipulation and monthly aggregation |
| `numpy` | Numerical operations and statistical sampling |
| `matplotlib` | Core chart creation |
| `seaborn` | Enhanced visual styling |
| `scikit-learn` | Linear Regression, Random Forest, model evaluation |

---

## How to Run

### Option A — Google Colab (recommended)
1. Upload `notebooks/PixelZone_BigData_Analytics.ipynb` to [Google Colab](https://colab.research.google.com)
2. Run all cells in order (Runtime → Run all)
3. The dataset CSV and chart images will be saved to your session

### Option B — Local
```bash
git clone https://github.com/your-username/pixelzone-big-data-analytics.git
cd pixelzone-big-data-analytics
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook notebooks/PixelZone_BigData_Analytics.ipynb
```

> Note: The notebook saves outputs to `../data/` and `../outputs/charts/` relative to the `notebooks/` folder. If running in Colab, update these paths or use `./` instead.

---

## Business Context

PixelZone Gaming Café targets Kuala Lumpur's 15–34 age group — students, young professionals, and tourists — with PC, console, and VR gaming in a dual-zone setup (Casual and VIP). The analytics in this project informed a **Cost-Benefit Analysis** recommending a 5-setup expansion with an estimated 19-month payback period and MYR 2,025/month net benefit post-recovery.

---

## License

This project was developed for academic purposes as part of IBM4208 – Big Data Analytics.
