# 🏠 Predicting London House Prices for Investment Strategy

## 🧠 Real-World Problem

Property investment in a competitive housing market like London requires identifying **undervalued properties** with strong potential for return. This project develops a **machine learning-based prediction engine** to:

- Estimate property prices from historical and listing data
- Identify the **top 200 homes** to invest in out of ~2000 listings

This was developed as part of the **Data Science Capstone Workshop** at London Business School.

---

## 🔍 Project Scope

- **Data**
  - **Training data** with historical sale prices
  - **Out-of-sample data** with current asking prices (used to test predictions and select investment properties)

- **Goals**
  1. Predict realistic prices for properties using ML algorithms
  2. Select 200 houses where predicted price exceeds asking price — i.e., **high return potential**

---

## 🛠 Tools & Technologies

- **Language**: R
- **Libraries**: 
  - `tidyverse`, `caret`, `glmnet`, `randomForest`, `caretEnsemble`
  - `Hmisc`, `janitor`, `lubridate`, `rpart.plot`

---

## 🔬 Machine Learning Models Used

- **Baseline**: Linear regression
- **Regularized model**: Lasso regression (via `glmnet`)
- **Tree-based**: Random forest
- **Ensemble**: Weighted combination of top models using `caretEnsemble`

Each model was tuned using cross-validation. Ensemble performance was benchmarked using RMSE on validation data.

---

## 💡 Investment Strategy

- Calculate **price delta** = Predicted Price - Asking Price
- Rank listings by descending price delta
- **Top 200 listings** were selected for investment, assuming largest discount to fair value

---

## 📁 Project Structure

```
.
├── roopa_yashaswini_Workshop_rmd_London_house_Prices_post.Rmd   # Full R Markdown analysis
├── data/
│   ├── london_house_prices_train.csv
│   └── london_house_prices_test.csv
├── README.md
```

---

## 📊 Key Results

- **Ensemble model** outperformed individual models (lowest RMSE)
- Top features affecting price: `area`, `postcode`, `type`, `size_category`, `floor`, `rooms`, `transport_rating`
- Final investment list includes **200 properties** with estimated return potential based on price underestimation

---

## 🚀 How to Run

1. Clone the repo and open `.Rmd` in RStudio
2. Ensure data files are in the `/data` folder
3. Install packages:
   ```r
   install.packages(c("tidyverse", "caret", "glmnet", "randomForest", "caretEnsemble", "janitor", "Hmisc", "lubridate"))
   ```
4. Knit the `.Rmd` to view full analysis and investment list