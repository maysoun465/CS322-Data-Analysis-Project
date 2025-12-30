# Environmental and Energy Patterns in Major US States: A Data Analysis Project

## Overview
This project presents a comprehensive analysis of environmental and energy factors across six major U.S. states: **California, Texas, Florida, New York, Tennessee, and the Carolinas** from 2023 to 2025. The study investigates the relationships between air quality (PM2.5), temperature, green space coverage, and electricity consumption, aiming to uncover patterns that affect environmental quality and energy usage.

Key objectives include:  
- Exploring how green space impacts air quality.  
- Understanding the effect of temperature on electricity consumption.  
- Comparing air pollution levels on weekdays versus weekends.

---

## Data Sources
The project integrates multiple data sources:

| Data Type | Source | Description |
|-----------|--------|-------------|
| Air Quality (PM2.5) | [OpenAQ](https://openaq.org/) | Hourly measurements aggregated to daily values |
| Temperature | [Meteostat API](https://meteostat.net/) | Daily max, min, and mean temperatures for selected cities |
| Electricity Consumption | [EIA](https://www.eia.gov/) | Daily electricity consumption in MWh |
| Green Space | [Google Earth Engine](https://earthengine.google.com/) | Monthly green space percentage per state |

---

## Methodology
1. **Data Collection & Loading**  
   - Gathered data from APIs and local CSV/JSON files.  
   - Loaded each dataset into separate pandas DataFrames.

2. **Data Preprocessing**  
   - Merged datasets by state and date.  
   - Handled missing values and interpolated temperature data.  
   - Corrected negative PM2.5 values using state-specific minimum positive values.  
   - Generated additional features: day of week, weekend indicator, normalized electricity, and Quality of Life (QoL) index.

3. **Exploratory Data Analysis (EDA)**  
   - Visualized distributions, trends, and correlations.  
   - Identified outliers (e.g., wildfire pollution events).  

4. **Statistical Analysis**  
   - Pearson correlation, t-tests, and linear regression models to quantify relationships.  

---

## Key Findings
- **Green Space and Air Quality:**  
  Slight negative correlation between green space and PM2.5 levels (`r ≈ -0.10`), suggesting modest improvement in air quality with higher green coverage.

- **Temperature and Electricity Consumption:**  
  Temperature significantly influences electricity demand, especially in warmer states. Overall correlation `r ≈ 0.39`.

- **Weekday vs Weekend Pollution:**  
  PM2.5 levels remain largely consistent, with minor differences in Texas (`p ≈ 0.034`).

- **Extreme Events:**  
  Wildfire-related PM2.5 spikes significantly affect air quality in states like California and Texas. These extreme events were retained in the dataset for analysis.
