🚲 Bike Demand Prediction for BoomBikes (Post-COVID US Market)

✅ Objective  
The objective of this project was to help **BoomBikes**, a US-based bike-sharing company, understand the key factors driving demand for shared bikes in the **post-COVID American market**.  
Using **multiple linear regression**, the goal was to identify statistically significant variables influencing daily bike demand so that the business can build a **data-driven expansion and revenue strategy** after the pandemic-induced downturn.

---

📊 About the Data  
The dataset contains **daily bike rental records** for the US market, including weather conditions, seasonal indicators, and temporal features.

- **Granularity:** Daily-level data  
- **Target Variable:** Total count of bike rentals per day  
- **Feature Types:**
  - Weather-related variables (temperature, windspeed, rainfall, weather conditions)
  - Time-based indicators (year, month, season, holidays)
  - Calendar and environmental attributes  

A detailed data dictionary was used to ensure correct interpretation of categorical and numerical variables.

---

## 🛠️ Data Cleaning & Preprocessing  

- Converted categorical variables (season, month, weather) into **dummy variables**
- Removed redundant and highly correlated features to prevent multicollinearity
- Scaled continuous variables to ensure coefficient comparability
- Ensured proper **train–test separation** to avoid data leakage

---

## 🔍 Feature Selection  

- Applied **Recursive Feature Elimination (RFE)** to identify the most impactful predictors
- Iteratively removed statistically insignificant variables
- Retained a **compact and interpretable feature set** with stable coefficients and acceptable multicollinearity

---

## 📈 Exploratory Data Analysis (EDA)  

Key insights from EDA:

- Bike demand shows a **year-on-year increase**, indicating post-pandemic recovery
- **Temperature** has a strong positive relationship with bike demand
- Adverse weather conditions such as **drizzle** and **cloudy days** reduce usage
- Demand is higher during **summer and winter**
- **Holidays** consistently show lower demand compared to working days

These insights directly guided feature selection and model interpretation.

---

## 🧠 Model Building  

- Built a **Multiple Linear Regression model** using the `statsmodels` library for interpretability  
- Evaluated multiple models and retained the one with:
  - Statistically significant coefficients
  - Stable performance
  - Clear business interpretability  

### Final Model Equation

\[
bikes = 0.190855 + (0.477737 \cdot temp) + (0.234132 \cdot year) + (0.094476 \cdot winter)
\]

\[
+ (0.090998 \cdot sep) + (0.062076 \cdot summer)
- (0.285031 \cdot drizzle) - (0.148098 \cdot windspeed)
\]

\[
- (0.096316 \cdot holiday) - (0.078741 \cdot cloudy)
- (0.055406 \cdot spring)
\]

---

## 🔑 Key Drivers of Demand  

**Strong positive drivers:**
- Temperature (largest positive impact)
- Year (reflecting post-pandemic recovery)
- Summer, winter, and September seasonality

**Negative drivers:**
- Drizzle (strongest negative impact)
- Windspeed
- Cloudy weather
- Holidays
- Spring season

---

## 💡 Business Recommendations  

- **Geographic Expansion:**  
  Prioritize regions with **warmer climates, longer summers, and lower rainfall**

- **Infrastructure Planning:**  
  Increase bike availability near **office hubs, corporate zones, and commercial areas**

- **Demand Smoothing:**  
  Introduce targeted promotions during **holidays** to mitigate demand drops

- **Brand Strategy:**  
  Align branding and fleet planning with seasonal and weather-driven demand patterns

---
