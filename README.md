# Automotive CO2 Emission Prediction Analysis

A data science and machine learning project focused on predicting carbon dioxide ($CO_2$) emissions from vehicles using engine and fuel performance metrics. This repository covers thorough Exploratory Data Analysis (EDA), addresses high feature multicollinearity, and evaluates multiple Linear Regression models to establish baseline and optimized performance.

---

## 📌 Project Overview
As global focus shifts toward environmental sustainability, understanding the core drivers of automotive emissions is vital. This project aims to build an interpretable machine learning model that accurately estimates a vehicle's $CO_2$ footprint. 

A core focus of this analysis is identifying and handling severe multicollinearity within fuel consumption variables to streamline data preparation and avoid inflated model variance.

---

## 📂 Data Source
The dataset used in this analysis is the **CO2 Emissions Canada** dataset, available on [Kaggle](https://www.kaggle.com/datasets/debajyotipodder/co2-emission-by-vehicles). 

It contains 7,385 records detailing vehicle attributes over a 7-year period across 12 core columns:
*   `Make` & `Model`: The manufacturer and specific vehicle line.
*   `Vehicle Class`: Category of vehicle (e.g., COMPACT, SUV - SMALL, MID-SIZE).
*   `Engine Size(L)`: Total cylinder volume displacement in Liters.
*   `Cylinders`: Number of engine cylinders (dropped during EDA due to heavy correlation with Engine Size).
*   `Transmission` & `Fuel Type`: Gearbox type and fuel classifications (Regular Gasoline, Premium, Diesel, Ethanol, Natural Gas).
*   `Fuel Consumption` metrics: Tracks City, Highway, and Combined performance ($L/100\text{ km}$ and $\text{mpg}$).
*   `CO2 Emissions(g/km)`: The target continuous variable.

---

## 🚀 Key Insights & Feature Selection
*   **Multicollinearity Triage:** High positive correlation exists between `Engine Size(L)` and `Cylinders`. `Cylinders` was dropped to prevent redundancy.
*   **The Fuel Consumption Trap:** Analyzing features revealed an almost perfect linear dependency between `Fuel Consumption City` and `Fuel Consumption Comb (L/100 km)` ($r = 0.994$). Because using them simultaneously introduces dangerous redundancy, individual isolated models were evaluated.
*   **Fuel Type Nuance:** While fuel types exhibit clear variances in visual distributions (e.g., Ethanol showing distinct separation), raw consumption metrics remain the strongest direct linear predictors of absolute $CO_2$ numbers.

---

## 🛠️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/automotive-co2-emission-prediction.git](https://github.com/YOUR_USERNAME/automotive-co2-emission-prediction.git)
   cd automotive-co2-emission-prediction
