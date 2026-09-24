# Seasonal Agriculture Performance – Data Analytics

An exploratory data analysis (EDA) of a farm-level agricultural dataset, examining how **season, irrigation method, environmental conditions and crop type** drive crop yield and farm profitability across 4,000 farm records in India.

## Project Overview

This project analyzes seasonal agricultural performance data to understand the relationships between weather conditions, soil health, irrigation practices, input usage, and farm economics (cost, revenue, profit). The analysis covers:

- Data quality checks (missing values, duplicates, invalid ranges, outliers)
- Exploratory analysis of yield distributions
- Seasonal performance comparison (Kharif, Rabi, Zaid)
- Crop × season yield analysis
- Environmental conditions by season (rainfall, temperature, humidity, soil moisture)
- Economic performance (revenue, cost, profit) by season
- Irrigation method and water-efficiency analysis
- Correlation analysis between environmental/input variables and yield/profit
- Top and bottom performing farms
- Disease and pest risk analysis by season and crop

Full write-up with charts, tables and recommendations is available in the accompanying project report (Word document).

## Dataset

- **File:** `seasonal_agriculture_performance_dataset.csv`
- **Size:** 4,000 rows × 28 columns
- **Link:** _[Add the dataset source link here]_ — the notebook loads the file from a local/Colab path (`/content/seasonal_agriculture_performance_dataset.csv`); the original source link was not included with the shared notebook, so please add it here once you have it (e.g. Kaggle, Google Drive, or your own repo link).

**Key columns:**

| Category | Columns |
|---|---|
| Identifiers / Location | `Farm_ID`, `State`, `District` |
| Crop & Season | `Crop`, `Season`, `Irrigation_Method` |
| Environment | `Farm_Area_Hectares`, `Rainfall_mm`, `Avg_Temperature_C`, `Humidity_pct`, `Sunlight_Hours_Day`, `Soil_pH`, `Soil_Moisture_pct` |
| Inputs | `Nitrogen_kg_ha`, `Phosphorus_kg_ha`, `Potassium_kg_ha`, `Fertilizer_kg_ha`, `Pesticide_Litre_ha`, `Seed_Quality_Score` |
| Output / Risk | `Yield_Tonnes_Ha`, `Production_Tonnes`, `Disease_Pest_Risk_pct` |
| Economics | `Market_Price_INR_Tonne`, `Total_Cost_INR`, `Revenue_INR`, `Profit_INR` |
| Water Use | `Water_Used_m3`, `Water_Efficiency_t_per_1000m3` |

**Coverage:** 8 states, 10 districts, 8 crops (Rice, Wheat, Maize, Cotton, Pulses, Groundnut, Chilli, Sugarcane), 3 seasons (Kharif, Rabi, Zaid), 4 irrigation methods (Flood, Rainfed, Drip, Sprinkler).

## Technologies Used

- **Python 3**
- **Pandas** – data loading, cleaning, and aggregation
- **NumPy** – numerical operations
- **Matplotlib** – base plotting
- **Seaborn** – statistical visualization (histograms, bar charts, box plots, heatmaps, scatter plots)
- **Jupyter Notebook** – analysis environment

## Setup / Run Instructions

1. **Clone or download this project** and make sure the notebook (`Seasonal_Agriculture_Performance_Data_Analytics.ipynb`) and the dataset CSV are in the same working directory (or update the file path in the notebook).

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate      # on Windows: venv\Scripts\activate
   ```

3. **Install the required packages:**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

4. **Update the dataset path** in the first data-loading cell if needed:
   ```python
   df = pd.read_csv('seasonal_agriculture_performance_dataset.csv')
   ```
   (The original notebook uses a Google Colab path, `/content/seasonal_agriculture_performance_dataset.csv` — change this to your local path.)

5. **Launch Jupyter and run the notebook:**
   ```bash
   jupyter notebook Seasonal_Agriculture_Performance_Data_Analytics.ipynb
   ```
   Run all cells from top to bottom (`Cell` → `Run All`) to reproduce the full analysis, including all charts and summary tables.

## Key Information / Findings

- **Kharif is the best-performing season** — highest mean yield (5.64 t/ha), highest mean profit (₹178,915), and highest rainfall/humidity — despite carrying the highest disease/pest risk.
- **Zaid is the weakest season** — lowest mean yield (4.67 t/ha) and the only season with a negative average profit (–₹24,805).
- **Water efficiency** (tonnes of yield per 1,000 m³ of water) is the strongest driver of both yield (r = 0.92) and profit (r = 0.49) — far ahead of rainfall, soil nutrients, or pesticide use.
- **Drip irrigation** outperforms Flood, Sprinkler, and Rainfed methods on yield, water efficiency, and profit, while **Flood irrigation** (the most common method) is the least efficient.
- **Sugarcane** dramatically outperforms all other crops in yield and profit; **Chilli** achieves strong profit from a comparatively low yield due to its market price.
- Data quality is strong: less than 1.2% missing values in any column, zero duplicate rows, and internally consistent profit calculations.

## Project Files

| File | Description |
|---|---|
| `Seasonal_Agriculture_Performance_Data_Analytics.ipynb` | Jupyter notebook containing the full analysis code |
| `seasonal_agriculture_performance_dataset.csv` | Source dataset (not included — add your own copy) |
| `Seasonal_Agriculture_Performance_Report.docx` | Full project report with narrative, tables, and charts |
| `README.md` | This file |
