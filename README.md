# 🚲 Cyclistic Bike-Share Case Study
### Google Data Analytics Capstone | Case Study 1
#### 📓 View Full Notebook
#### 👉 [Run & view on Kaggle](https://www.kaggle.com/code/YOUR_USERNAME/cyclistic-bike-share-analysis)
---

## 🎯 Business Task

Cyclistic is a fictional Chicago bike-share company with 5,824 bikes and 692 stations. Finance has determined that annual members are more profitable than casual riders. The Director of Marketing wants to convert casual riders into members.

**The question this analysis answers:**
> How do annual members and casual riders use Cyclistic bikes differently?

---

## 📦 Dataset

| Property | Detail |
|----------|--------|
| **Source** | https://divvy-tripdata.s3.amazonaws.com/index.html |
| **Provider** | Motivate International Inc. (real Divvy bike data) |
| **Period** | Most recent 12 months (12 CSV files, one per month) |
| **Size** | ~5 million rows combined |
| **Licence** | [Divvy Data Licence Agreement](https://www.divvybikes.com/data-license-agreement) |
| **Privacy** | No personally identifiable information |

---

## 🗂️ Structure

```
cyclistic_case_study/
├── cyclistic_bike_share_case_study.ipynb   ← Main notebook
├── README.md
└── output/
    ├── 01_volume_and_duration.png
    ├── 02_seasonal_heatmap.png
    └── 03_top_stations.png
```

---

## 🛠️ Kaggle Setup

1. Search **"divvy tripdata"** on Kaggle and attach the dataset
2. Upload `cyclistic_bike_share_case_study.ipynb`
3. Run Cell 2 (path finder) first — copy the folder path it prints
4. Update `DATA_PATH` in Cell 3 if needed
5. Run all cells

---

## 🧪 Notebook Structure (Ask → Prepare → Process → Analyse → Share → Act)

### 1️⃣ Ask
Defines the business task, key stakeholders, and success criteria. Sets up the three guiding questions for the marketing programme.

### 2️⃣ Prepare
Loads all 12 monthly CSV files and concatenates them into one dataset. Assesses data quality against the ROCCC framework (Reliable, Original, Comprehensive, Current, Cited). Documents known limitations including the inability to link rides to individual customers.

### 3️⃣ Process
Cleaning steps — all documented with reasons:
- Dates parsed from string to `datetime64`
- `ride_length_min` calculated from start/end timestamps
- Time features derived: `hour_of_day`, `day_of_week`, `month`, `season`
- Rides with duration ≤ 0 removed (impossible — system errors)
- Rides < 1 minute removed (false starts / immediate re-docks)
- Rides > 24 hours removed (lost/stolen bikes per Cyclistic policy)
- Null timestamps removed

### 4️⃣ Analyse
Five dimensions compared between members and casual riders:
- Overall ride volume and average duration
- Day-of-week patterns
- Hour-of-day patterns
- Monthly and seasonal patterns
- Bike type preferences
- Top start stations

### 5️⃣ Share
Eight charts, each answering a specific question:
1. Total rides and average duration by rider type
2. Rides by day of week (grouped bar)
3. Average duration by day of week (line)
4. Rides by hour of day with commute windows highlighted
5. Monthly trend line chart
6. Seasonal heatmap
7. Bike type preference (grouped bar)
8. Ride duration box plot (notched)
9. Top 10 start stations by rider type
10. Executive summary dashboard

Consistent colour coding throughout: 🔵 Blue = Members · 🟡 Amber = Casuals

### 6️⃣ Act
Three data-backed recommendations:

| Recommendation | Rationale |
|---------------|-----------|
| Weekend Membership Tier | Casuals peak on weekends — a weekend-only membership meets them where they already are |
| Seasonal Conversion Campaign | Target April–May before casual ridership peaks; use personalised ride history data in messaging |
| Station-Level Activation | Deploy touchpoints at top casual stations (leisure/lakefront); most cost-efficient conversion channel |

---

## 📈 Key Findings

| Finding | Evidence |
|---------|----------|
| Members ride more often; casuals ride longer per trip | Volume and duration charts |
| Members peak mid-week; casuals peak on weekends | Day-of-week analysis |
| Members show classic commute spikes at 8am and 5pm | Hour-of-day chart |
| Casual ridership drops steeply in winter; members remain stable | Seasonal heatmap |
| Casual riders concentrate at leisure/tourist stations | Top stations comparison |
| Only casual riders use docked bikes | Bike type analysis |

---

## 💡 What I Would Do With More Time
- Pricing data to calculate actual savings of membership vs. casual passes
- Tourist vs. local separation using postal code (if available)
- Churn/conversion prediction model on casual usage patterns

---

*Built by Jessica Dan-Odhomo · [LinkedIn](https://www.linkedin.com/in/jessica-dan-odhomo) · [GitHub](https://github.com/Teekaayyy)*
