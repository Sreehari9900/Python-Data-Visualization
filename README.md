<div align="center">

# 🚕 NYC Taxi Data Visualization

**An exploratory data analysis project using Python, Pandas, Matplotlib, and Seaborn**

<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
<img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge" alt="Matplotlib">
<img src="https://img.shields.io/badge/Seaborn-Statistical%20Plots-4C72B0?style=for-the-badge" alt="Seaborn">
<img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter Notebook">

**A practical exploration of New York City taxi trips, fares, payment methods, boroughs, and trip distances.**

</div>

---

## 📌 Project Overview

This assignment explores the **Seaborn `taxis` dataset** and demonstrates a complete introductory visualization workflow: loading data, checking and handling missing values, and communicating patterns with ten charts built using Matplotlib, Pandas plotting, and Seaborn.

## 🎯 Objectives

- Inspect missing values and prepare fields for analysis.
- Compare fare totals and trip volumes across pickup boroughs.
- Explore trip distance, fare, tip, and total relationships.
- Examine payment-method distributions and fare patterns.
- Practice choosing chart types for time series, categories, distributions, and correlations.

## 🧰 Tools and Technologies

| Tool | Role |
| --- | --- |
| Python | Analysis language |
| Pandas | Data cleaning, grouping, and plotting |
| Matplotlib | Core chart construction and presentation |
| Seaborn | Statistical plots and built-in `taxis` dataset |
| Jupyter Notebook | Interactive code and analysis |

## 📂 Repository Structure

```text
.
├── README.md
├── Python - Data Visualization.ipynb
└── Visual_Outputs/
    ├── Matplotlib_Pandas_Visualizations/
    │   ├── 01_line_chart_fare_over_time.png
    │   ├── 02_bar_chart_total_fare_by_borough.png
    │   ├── 03_pie_chart_payment_method.png
    │   ├── 04_histogram_trip_distance.png
    │   └── 05_box_plot_tip_by_borough.png
    └── Seaborn_Visualizations/
        ├── 06_count_plot_trips_by_borough.png
        ├── 07_scatter_plot_distance_vs_fare.png
        ├── 08_heatmap_correlation.png
        ├── 09_pair_plot_top5_pickup_zones.png
        └── 10_violin_plot_fare_by_payment.png
```

## 🧹 Data Preparation

The notebook loads the dataset with `seaborn.load_dataset("taxis")`, checks null counts, and applies the following strategies:

- **Categorical fields** (`payment`, pickup/dropoff zones, and pickup/dropoff boroughs): fill missing values with each column's mode.
- **Numeric fields** (`passengers`, `distance`, `fare`, `tip`, `tolls`, and `total`): fill missing values with each column's median.
- **Critical timestamps** (`pickup` and `dropoff`): remove rows where either timestamp is missing.
- Convert `pickup` to datetime and sort by pickup time before creating the fare-over-time chart.


## 🔄 Project Workflow</h2>

<div align="center">

<table>
<tr><td align="center" bgcolor="#E8F1FF"><b>Dataset Loading</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Data Exploration</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Missing Value Analysis</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Data Cleaning and Imputation</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Date Conversion</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Exploratory Data Analysis</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Matplotlib Visualizations</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#E8F1FF"><b>Seaborn Visualizations</b></td></tr>
<tr><td align="center">⬇️</td></tr>
<tr><td align="center" bgcolor="#DDF5E4"><b>Final Results</b></td></tr>
</table>

</div>

---

## 🧹 Dataset & Cleaning Process

**Dataset: sns.load_dataset("taxis") with 6,433 trips × 14 columns (pickup/dropoff time, passengers, distance, fare, tip, tolls, total, payment, zones and boroughs)**.

Step	Action:

1️⃣	Checked missing values with df.isnull().sum(): payment (44), pickup_zone (26), dropoff_zone (45), pickup_borough (26), dropoff_borough (45).

2️⃣	Filled categorical columns with the mode.

3️⃣	Filled numerical columns with the median.

4️⃣	Dropped rows missing critical pickup / dropoff timestamps.

5️⃣	Verified the result: 0 missing values, final shape (6433, 14).

--- 
## Assignment Tasks and Implementation

| # | Task | Tool | Implementation | Status |
| :-: | --- | --- | --- | :---: |
| 1 | Load the `taxis` dataset | Seaborn | `sns.load_dataset("taxis")` | Complete |
| 2 | Handle missing values | Pandas | `fillna()` with mode/median; `dropna()` on `pickup` and `dropoff` | Complete |
| 3 | Fare over time | Matplotlib | Convert `pickup` with `pd.to_datetime()`, sort by time, then `plt.plot()` | Complete |
| 4 | Total fare by borough | Pandas Plot | `groupby("pickup_borough")["fare"].sum().plot(kind="bar")` | Complete |
| 5 | Trips by payment method | Pandas Plot | `value_counts().plot(kind="pie", autopct="%1.1f%%")` | Complete |
| 6 | Trip distance histogram | Matplotlib | `plt.hist(df["distance"], bins=30)` | Complete |
| 7 | Tip by borough | Seaborn | `sns.boxplot(x="pickup_borough", y="tip")` | Complete |
| 8 | Trips per borough | Seaborn | `sns.countplot(x="pickup_borough")` | Complete |
| 9 | Distance versus fare | Seaborn | `sns.scatterplot()` with `hue="pickup_borough"` | Complete |
| 10 | Correlation heatmap | Seaborn | Correlation matrix with `sns.heatmap(annot=True, cmap="coolwarm")` | Complete |
| 11 | Pair plot for top five pickup zones | Seaborn | `sns.pairplot()` with `hue="pickup_zone"` | Complete |
| 12 | Fare by payment method | Seaborn | `sns.violinplot(x="payment", y="fare")` | Complete |

---

## 🚀 Getting Started

### Requirements

- Python 3.9 or newer
- Jupyter Notebook or JupyterLab
- `pandas`, `matplotlib`, and `seaborn`

### Install dependencies

```bash
python -m pip install pandas matplotlib seaborn jupyter

```

### Run the notebook

```bash
jupyter notebook "Python - Data Visualization.ipynb"
```

Run the cells from top to bottom. Seaborn may need an internet connection the first time it downloads the built-in `taxis` dataset.

## 📝 Notes

- The notebook is the executable source for the analysis; the PNG files are the exported visual results.
- This is an educational exploratory analysis. Imputing values can affect distributions and summary statistics, so results should be interpreted in light of the cleaning choices.

---

## 💡 Key Learning Outcomes</h2>

- Learned to explore and understand structured datasets.
- Practiced missing value identification and imputation.
- Improved knowledge of Pandas and NumPy.
- Created different visualizations using Matplotlib and Seaborn.
- Understood data distributions, correlations and relationships.
- Gained practical experience in exploratory data analysis.

----
  
## 👨‍💻 Author

**Y Srihari**

**Aspiring Data Analyst**  **Python · Data Analysis · Data Visualization**

<a href="https://github.com/Sreehari9900"><img src="https://img.shields.io/badge/GitHub-Visit%20My%20Profile-181717?style=for-the-badge&logo=github&logoColor=white" alt="Visit GitHub profile"></a>
<a href="mailto:sreens9014@gmail.com"><img src="https://img.shields.io/badge/Gmail-Email%20Me-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email Sree Hari">


**Made with ❤️ Python • Pandas • Matplotlib • Seaborn**

