# ADS506-FinalProject-Team4
# CO2 Time Series Forecasting with ARIMA in R

## Overview
This project performs time series forecasting of atmospheric CO2 concentrations using both automatic and manual ARIMA models in R. The analysis uses monthly CO2 measurements from Mauna Loa Observatory.

## Dataset
- **Source**: Mauna Loa Observatory CO2 measurements (`co2_mm_mlo.csv`)
- **Time Range**: March 1958 - August 2025
- **Frequency**: Monthly observations

### Key Columns
- `average`: Average CO2 concentration (ppm)
- `deseasonalized`: Seasonally adjusted CO2 values (ppm)

## Installation

### Required Libraries
```r
install.packages("forecast")
library(forecast)
```

## Data Preparation

### Step 1: Create Clean CSV File (One-Time Setup)
The original file has 40 header lines that must be removed:

```r
# Uncomment these lines for first-time setup
# lines <- readLines("co2_mm_mlo.csv")
# new_lines <- lines[41:length(lines)]
# writeLines(new_lines, "co2_clean.csv")
```

### Step 2: Load Data
```r
data <- read.csv("co2_clean.csv")

# Verify data loaded correctly
head(data)
dim(data)
colnames(data)
```

## Automatic ARIMA (Current Implementation)

### Model 1: Auto ARIMA on Raw CO2 Data

```r
# Create time series object
ts_data <- ts(data$average, 
              start = c(1958, 3),    # Start: March 1958
              frequency = 12)         # Monthly data

# Fit ARIMA model (automatically finds best parameters)
arima_model <- auto.arima(ts_data)
summary(arima_model)

# Forecast next 24 months
forecast_result <- forecast(arima_model, h = 24)
print(forecast_result)

# Plot the forecast
plot(forecast_result, 
     main = "CO2 PPM Forecast",
     xlab = "Year",
     ylab = "CO2 PPM")
```
