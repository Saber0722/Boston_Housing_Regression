# Boston Housing Regression Analysis

This project performs regression analysis on the [Boston Housing Dataset](https://www.cs.toronto.edu/~delve/data/boston/bostonDetail.html) to predict house prices (`medv`). It explores both linear and polynomial regression models, with hyperparameter tuning using `GridSearchCV` to optimize performance.

## Project Overview
The goal of this project is to build and evaluate regression models to predict the median value of owner-occupied homes (`medv`) in Boston using various neighborhood features. The analysis includes:
- Linear regression as a baseline.
- Polynomial regression to capture non-linear relationships.
- Hyperparameter tuning with `GridSearchCV` to optimize the polynomial degree and regularization strength.
- Evaluation using R² score, Mean Squared Error (MSE), and Mean Absolute Error (MAE).

## Dataset Description
The Boston Housing Dataset is a classic and widely-used resource in machine learning and statistics. Compiled from census data, it provides a comprehensive look into the housing landscape of Boston, Massachusetts, focusing on key attributes influencing housing prices. The dataset contains 506 samples and 14 columns (13 features + 1 target).

### Features
- **crim**: Per capita crime rate by town.
- **zn**: Proportion of large residential lots (over 25,000 sq. ft.).
- **indus**: Proportion of non-retail business acres per town.
- **chas**: Binary variable indicating if the property is near Charles River (1 for yes, 0 for no).
- **nox**: Concentration of nitrogen oxides in the air.
- **rm**: Average number of rooms per dwelling.
- **age**: Proportion of old owner-occupied units built before 1940.
- **dis**: Weighted distances to Boston employment centers.
- **rad**: Index of accessibility to radial highways.
- **tax**: Property tax rate per $10,000.
- **ptratio**: Pupil-teacher ratio by town.
- **b**: 1000(Bk - 0.63)^2 where Bk is the proportion of Black residents by town.
- **lstat**: Percentage of lower-status population.

### Target
- **medv**: Median value of owner-occupied homes in $1000s (the variable we aim to predict).

These features provide valuable insights into the characteristics of neighborhoods that influence housing prices, making this dataset ideal for exploring patterns, building predictive models, and understanding the factors affecting urban housing markets.

## Files
- `Regression_Analysis.ipynb`: Jupyter Notebook containing the full analysis, including data loading, preprocessing, model training, evaluation, and visualization.
- `BostonHousing.csv`: The dataset used for the analysis.

## Methodology
1. **Data Preprocessing**:
   - Loaded the dataset using `pandas`.
   - Split the data into training and test sets (80-20 split) using `train_test_split`.

2. **Linear Regression**:
   - Trained a baseline linear regression model using `LinearRegression` from scikit-learn.
   - Evaluated performance using R², MSE, and MAE.

3. **Polynomial Regression**:
   - Applied `PolynomialFeatures` (degree 2) to capture non-linear relationships.
   - Trained a linear regression model on the transformed features.
   - Evaluated and visualized predictions (scatter plot of actual vs. predicted values).

4. **Hyperparameter Tuning**:
   - Used `GridSearchCV` to optimize:
     - Regularization strength (`ridge__alpha`: 0.01, 0.1, 1.0, 10.0).
   - Applied `StandardScaler` to normalize features before polynomial transformation.
   - 
## Results
- **Linear Regression**:
  - R² Score: 0.72
  - The model captured linear relationships but missed non-linear patterns.

- **Polynomial Regression (Degree 2)**:
  - R² Score: 0.83
  - Improved performance by capturing non-linear relationships, but still room for optimization.

- **Random Forest Regressor**:
  - R² Score: 0.88
  - Improved performance by capturing non-linear relationships.

## Setup Instructions
To run this project locally:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Saber0722/Boston_Housing_Regression.git
   cd Boston_Housing_Regression
