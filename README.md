### Predicting Housing Prices: Phase 2 - Regression

#### Objective:
In the second phase of the project, the primary goal was to create models that predict the exact price of houses. This phase dealt with a regression task where the target variable was the exact prices of the houses in dollars.

#### Data:
The dataset used contained various housing attributes, totaling 81 columns. These attributes captured information on dwelling type, zoning classification, area, quality of diverse amenities, and more.

#### Preprocessing & Feature Engineering:
- **Handling Missing Values**:
  - Numerical columns: Median imputation was employed.
  - Categorical columns: Missing values were filled using a constant value 'missing'.
- **Encoding & Scaling**:
  - Categorical features underwent one-hot encoding.
  - Numerical features were standardized using the StandardScaler.

#### Feature Selection:
Multiple feature selection methods were explored:
- VarianceThreshold
- SelectKBest
- RFECV (Recursive Feature Elimination with Cross-Validation)
- SelectFromModel

#### Model Building & Evaluation:
The primary model used for regression was the Random Forest Regressor. This model was trained on datasets processed by each of the feature selection methods mentioned above.

- Performance metrics employed for evaluation:
  - Root Mean Square Error (RMSE)
  - R-squared (\( R^2 \))

A snapshot of the models' performance:
- VarianceThreshold: RMSE \( \approx \) 26,887, \( R^2 \approx \) 0.896
- SelectKBest: RMSE \( \approx \) 28,323, \( R^2 \approx \) 0.885
- RFECV: RMSE \( \approx \) 26,307, \( R^2 \approx \) 0.901
- SelectFromModel: RMSE \( \approx \) 27,143, \( R^2 \approx \) 0.894

#### Hyperparameter Tuning:
Grid Search was applied to the Random Forest Regressor to find the optimal set of hyperparameters. The best parameters identified across the feature selection methods were:
- `max_depth`: None
- `min_samples_leaf`: 2
- `min_samples_split`: 2
- `n_estimators`: 100

### Error Analysis:
- Additional regression metrics such as RMSE (Root Mean Square Error), MAE (Mean Absolute Error), and MBD (Mean Bias Deviation) were employed to provide a deeper understanding of model errors.

#### Conclusion:
The model trained with features selected using RFECV performed the best in terms of RMSE and \( R^2 \). However, the differences in performance across the models were not substantial. In real-world scenarios, the choice of model could also consider factors like computational efficiency, interpretability, and ease of deployment.
