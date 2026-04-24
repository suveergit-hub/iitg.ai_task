# Electricity Demand Prediction

This project aims to predict hourly electricity demand using historical power demand data and weather (temperature) information. The model is trained on data from 2015 to 2023 and evaluated on data from 2024 onwards, using a Random Forest Regressor.

**Author:** Suveer Shandilya

 By combining historical demand data with temperature records, this project builds a machine learning model to forecast future electricity needs accurately. 

### Key Steps:
1. **Data Loading & Cleaning**: 
   - Handles missing values, impossible spikes (e.g., removing outliers outside the 0.1th and 99.9th percentiles).
   - Resamples data to ensure exactly one row per hour (at the `:00` mark).
2. **Weather Data Integration**: 
   - Merges historical temperature data to provide additional context for the model.
3. **Feature Engineering**: 
   - **Calendar Features**: Hour, day of the week, month, and weekend flags.
   - **Cyclical Features**: Sine and cosine transformations for hours and months to capture cyclical patterns.
   - **Lag Features**: Past demand from 1h, 2h, 3h, 24h, and 168h ago.
   - **Rolling Averages**: Moving averages over the last 6 hours, 24 hours, and 7 days.
4. **Modeling**: 
   - Trains a `RandomForestRegressor` to forecast the next hour's demand.
5. **Evaluation**: 
   - Our  Mean Absolute Percentage Error (MAPE) came to be 2.93% and it has been visualised by graphs.

## Datasets
The project uses the following datasets:
* `PGCB_date_power_demand.xlsx` - Contains historical electricity generation and demand (MW).
* `weather_data.xlsx` - Contains historical hourly temperature data.


