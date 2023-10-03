## Predicting Housing Prices: Phase 2 - Regression

### Objective:
In the second phase of the project, the focus shifts to predicting the exact price of a house. This is a regression task where the target variable is continuous, representing house prices in dollars.

### Data:
The dataset encompasses various features associated with housing, including the type of dwelling, zoning classification, area, quality of different amenities, and many more, amounting to 81 columns.

### Preprocessing & Feature Engineering:
- **Handled missing values**:
  - Numerical columns: Median imputation was employed.
  - Categorical columns: The most frequent value was utilized for imputation.
- **Encoding & Scaling**:
  - One-hot encoded categorical features.
  - Scaled numerical features using the StandardScaler.
- **Feature Selection**:
  - Three distinct methods were examined: VarianceThreshold, SelectKBest, and RFECV.

### Model Building & Evaluation:
- **Gradient Boosting Regressor**: This model was chosen for its capacity to handle complex datasets and its ability to provide accurate predictions.
- **Performance Metrics**:
  - R-squared (\( R^2 \)) was employed to evaluate the model's explanatory power.
  - MAPE (Mean Absolute Percentage Error) was used to understand prediction accuracy.
- **Models and their performance**:
  - **Initial Models**:
    - VarianceThreshold: \( R^2 = 0.900 \), MAPE = 0.099
    - SelectKBest: \( R^2 = 0.890 \), MAPE = 0.108
    - RFECV: \( R^2 = 0.910 \), MAPE = 0.099
  - **After PCA**:
    - VarianceThreshold: \( R^2 = 0.894 \), MAPE = 0.107
    - SelectKBest: \( R^2 = 0.894 \), MAPE = 0.112
    - RFECV: \( R^2 = 0.879 \), MAPE = 0.105
  - **After Hyperparameter Tuning**:
    - VarianceThreshold: \( R^2 = 0.898 \), MAPE = 0.105
    - SelectKBest: \( R^2 = 0.881 \), MAPE = 0.116
    - RFECV: \( R^2 = 0.900 \), MAPE = 0.099

### Hyperparameter Tuning:
- **Random Search** and **Grid Search** methods were utilized to identify optimal hyperparameters for the Gradient Boosting Regressor.
- The best hyperparameters were determined for each feature selection method.

### Error Analysis:
- Additional regression metrics such as RMSE (Root Mean Square Error), MAE (Mean Absolute Error), and MBD (Mean Bias Deviation) were employed to provide a deeper understanding of model errors.

### Conclusion:
The RFECV model consistently emerged as the top performer across different stages of the project. It not only demonstrated the highest \( R^2 \) but also showcased the lowest MAPE, marking it as the most accurate and well-calibrated model for this regression task.
