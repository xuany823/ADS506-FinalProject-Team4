# 📈 ADS506 Final Project – Mauna Loa Atmospheric CO₂ Forecasting
**University of San Diego – Applied Data Science (ADS 506)**  
**Team 4 – Final Team Project**

---

## 📌 Project Overview  
This repository contains the full codebase and documentation for our ADS-506 Final Team Project. Our team analyzes the **monthly atmospheric CO₂ concentrations recorded at Mauna Loa Observatory in Hawaii**, using time series forecasting techniques to understand long-term trends and project future CO₂ levels.

📄 This repo includes our modeling scripts, exploratory analysis, data processing code, and fully reproducible workflow.

---

## 🌍 Dataset Description
We use the official **NOAA ESRL / NOAA Global Monitoring Laboratory (GML)** *Monthly CO₂ dataset* collected from Mauna Loa, Hawaii. This dataset is one of the most well-known and heavily used global climate monitoring datasets.

### **Dataset Source**
NOAA Global Monitoring Laboratory  
Atmospheric CO₂, Mauna Loa Observatory – Monthly Dataset  
https://gml.noaa.gov/ccgg/trends/data.html
### **Our Dataset File**
`co2.csv` (stored in the project root directory)

### **Dataset Variables**
| Column | Description |
|--------|-------------|
| `year` | Year of observation |
| `month` | Month of observation |
| `decimal_date` | Decimal representation of the date |
| `average` | Monthly average CO₂ concentration (ppm) |
| `deseasonalized` | CO₂ with seasonal effects removed |
| `ndays` | Number of contributing days |
| `sdev` | Standard deviation |
| `unc` | Measurement uncertainty |

---

## 📁 Repository Structure
ADS506-FinalProject-Team4/main   
── co2.csv                     # Primary dataset (NOAA monthly CO₂)   
── co2.qmd                     # Main analysis notebook (Quarto)   
── README.md                   # Project documentation  
── LICENSE   
── .gitignore   

---

## ▶️ How to Use This Repository

### **1. Clone the repository**
```bash
git clone https://github.com/TEAM_REPO_URL/ADS506-FinalProject-Team4.git
cd ADS506-FinalProject-Team4

### **2. Open the project in RStudio **
	•	Open the .Rproj file (recommended), OR
	•	Open the entire project folder in RStudio

3. Load the dataset in R

Because co2.csv is included directly in the repository, all team members can load it using a relative path:
library(readr)
co2 <- read_csv("co2.csv")

⚠️ Important: Do NOT use absolute paths (e.g., /Users/.../Desktop/...).
Relative paths ensure reproducibility for all collaborators.



🔧 Requirements

Install required packages:
install.packages(c("tidyverse", "tsibble", "fable", "feasts", "lubridate"))

library(tidyverse)
library(tsibble)
library(fable)
library(feasts)
library(lubridate)
library(readr)

🤝 Collaboration Workflow (GitHub)

Our team follows GitHub best practices for version control, as required by the ADS 506 final project.

Branching Strategy
	•	main → stable, finalized code
	•	Development branches:
	•	michelle-dev
	•	Vinh-dev
	•	Duy-dev

Workflow Example：
git pull origin main
git checkout michelle-dev

# Make changes locally
git add .
git commit -m "Updated ARIMA model section"

# Push work
git push origin michelle-dev

# Submit Pull Request on GitHub

All PRs require teammate review before merging.

🎯 Project Objectives

Our technical analysis focuses on:
	•	Long-term atmospheric CO₂ trend analysis
	•	Seasonal decomposition & pattern recognition
	•	Applying multiple forecasting approaches:
	•	TSLM (trend + seasonality)
	•	ETS
	•	ARIMA & Auto-ARIMA
	•	Time series cross-validation with rolling-origin
	•	Evaluating models using RMSE, MAE, MAPE
	•	Forecasting future atmospheric CO₂ concentrations
	•	Crafting a compelling data story for a non-technical audience


📚 Citation

Required NOAA citation:

NOAA Global Monitoring Laboratory. (2024). Trends in Atmospheric Carbon Dioxide. Retrieved from https://gml.noaa.gov/ccgg/trends/data.html


🧠 Academic Integrity Disclosure

AI-assisted tools (e.g., ChatGPT, DeepSeek) were used for:
	•	Draft editing
	•	Documentation writing (including this README)
	•	Code explanation and debugging

All code and modeling decisions were reviewed and validated by team members.


