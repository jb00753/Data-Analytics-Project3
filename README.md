Georgia Real Estate Price Analysis — Refined Model
- A follow-up to Project 2, using Gradient Boosting to significantly improve price prediction accuracy on the same Georgia real estate dataset. Also includes a working price predictor that estimates a home's sale price from user-defined inputs.

- Tech Stack: Python | Pandas | NumPy | Matplotlib | Seaborn | Scikit-learn


- Problem Statement
  
  - How do property characteristics combine to determine home sale prices in Georgia, and which factors are most influential?

- Dataset

  - Source: Georgia real estate listings, first half of 2021
  - Size: 13,804 rows × 39 columns
  - Key Features Used: livingArea, bathrooms, bedrooms, yearBuilt, hasGarage, garageSpaces, pool, homeType, county, latitude, longitude


- Motivation
  - Project 2 used a Linear Regression model and achieved an R² of 0.55, leaving 45% of price variation unexplained. This project aimed to improve that by:

    - Switching to a Gradient Boosting Regressor to better capture non-linear relationships
    - Reintroducing previously dropped features (latitude, longitude, garageSpaces) to add predictive power


- Approach

  - Applied the same data cleaning pipeline as Project 2
  - Reintroduced select features that were dropped in the previous iteration
  - Trained a Gradient Boosting model using Scikit-learn
  - Evaluated performance using R², RMSE, and MAE
  - Saved the final model using pickle for reuse
  - Built a price predictor that accepts custom property inputs and returns an estimated sale price


- Results
  - Metric: Project 2 (Linear Regression) R² Score: 0.55 MAE: ~$84,480 RMSE: ~$117,500
  - Project 3 (Gradient Boosting) R² Score: 0.72 MAE: ~$63,189 RMSE: ~$93,093

R² improved by 17 percentage points, meaning the model now explains 72% of home price variation
MAE improved by over $21,000 per prediction
Adding features back in (latitude, longitude, garageSpaces) contributed meaningfully to the improvement


- Price Predictor
The saved model can generate price estimates from custom inputs. For example, a 2,000 sq ft, 3-bed/2.5-bath single family home built in 2018 with a garage in Fulton County predicts at:

Estimated Sale Price: $599,270


- Limitations & Future Work

  - Dataset is still limited to Georgia listings from early 2021
  - A broader, more recent dataset would likely improve generalizability further
  - Future iterations could explore hyperparameter tuning and additional ensemble methods


Screenshots:

![Screenshot](https://github.com/jb00753/Data-Analytics-Project3/blob/main/assets/Screenshot%20(181).png?raw=true)
![Screenshot](https://github.com/jb00753/Data-Analytics-Project3/blob/main/assets/Screenshot%20(182).png?raw=true)
