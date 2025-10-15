# Rainfall Prediction using Machine Learning

## Project Overview
This project predicts the likelihood of rainfall in Australia based on historical weather data.  
We use the **Australian Government's Bureau of Meteorology** dataset (sourced via Kaggle) containing daily weather observations from **2008 to 2017**.  
The model predicts whether it will rain **“Tomorrow”** given today’s weather conditions.


## Dataset Information
- **Source**: [BOM Climate Data](http://www.bom.gov.au/climate/dwo/) and [Kaggle Weather Dataset](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package/)  
- **Time period**: 2008 – 2017  
- **Target Variable**: `RainTomorrow` (Yes/No)

### Fields
| Field | Description | Unit |
|-------|-------------|------|
| Date | Date of the observation | YYYY-MM-DD |
| Location | City/region of the observation | Text |
| MinTemp | Minimum temperature | °C |
| MaxTemp | Maximum temperature | °C |
| Rainfall | Rain amount | mm |
| Sunshine | Bright sunshine | hours |
| WindGustDir | Direction of strongest wind gust | Compass point |
| WindGustSpeed | Speed of strongest gust | km/h |
| Humidity9am / Humidity3pm | Humidity levels | % |
| Pressure9am / Pressure3pm | Air pressure | hPa |
| Cloud9am / Cloud3pm | Cloud cover | Eighths |
| Temp9am / Temp3pm | Temperatures | °C |
| RainToday | Rain occurrence today (Yes/No) | Binary |
| RainTomorrow | Rain occurrence tomorrow (Yes/No) | Binary |

## Project Steps
1. **Data Preprocessing**
   - Cleaned missing values
   - Mapped categorical values (e.g., wind directions, Yes/No)
   - Extracted **Season** from the Date column
   - Selected features and target variable

2. **Train-Test Split**
   - Data divided into training (80%) and testing (20%)  
   - Stratified split to balance Yes/No target classes

3. **Feature Engineering**
   - Numerical features scaled using `StandardScaler`
   - Categorical features one-hot encoded with `OneHotEncoder`

4. **Pipeline & Models**
   - Built a pipeline with preprocessing + classifier
   - Trained and compared two models:
     - **RandomForestClassifier**
     - **LogisticRegression**

5. **Hyperparameter Tuning**
   - Used `GridSearchCV` with cross-validation
   - Tuned hyperparameters (n_estimators, max_depth for RF; solver, penalty for LR)

6. **Evaluation**
   - Accuracy Score
   - Classification Report
   - Confusion Matrix
   - Feature Importances (for RandomForest)


## Results
- **Random Forest** achieved higher accuracy with feature importance insights.  
- **Logistic Regression** provided explainability with comparable performance.  
- Both models were compared to ensure robustness.


## Next Steps
- Handle missing data more effectively (e.g., imputation techniques)  
- Try more advanced models (e.g., Gradient Boosting, XGBoost)  
- Explore regional weather prediction (train models for specific cities)  
- Deploy as a web app (e.g., Flask, FastAPI, or Streamlit)
  

## Tech Stack
- Python (pandas, numpy, scikit-learn, matplotlib, seaborn)  
- Jupyter Notebook  
