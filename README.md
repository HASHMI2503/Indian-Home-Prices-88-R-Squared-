# Indian-Home-Prices-88-R-Squared-
Explore India House Price Prediction using PyForest. Achieved an 88% R-Squared accuracy through advanced regression. Uncover insights into the real estate market. #DataScience #PyForest #HousePricePrediction 🏡✨

## Summary

1. **Data Import and Cleaning:**
   - Imported the dataset and converted the 'number of bathrooms' column to an integer type.
   - Dropped the 'id' column for simplicity.

2. **PCA on Numeric Columns:**
   - Applied Principal Component Analysis (PCA) to numeric columns, excluding 'date' and the output column ('price').

3. **Two Experimental Paths:**
   - **Path 1:** Conducted analysis on all columns using PyForest for automatic feature selection.
   - **Path 2:** Removed columns with low PCA variance to reduce complexity, resulting in a similar model performance but with reduced time complexity.

4. **Model Comparison**

### Path 1: All Columns
| Model                               | Adjusted R-Squared | R-Squared | RMSE      | Time Taken (s) |
|-------------------------------------|--------------------|-----------|-----------|-----------------|
| HistGradientBoostingRegressor       | 0.88               | 0.88      | 128699.89 | 0.77            |
| XGBRegressor                        | 0.88               | 0.88      | 131244.14 | 0.78            |
| LGBMRegressor                       | 0.88               | 0.88      | 131667.67 | 0.68            |
| ... (Top models)                    | ...                | ...       | ...       | ...             |

### Path 2: Reduced Columns
| Model                               | Adjusted R-Squared | R-Squared | RMSE      | Time Taken (s) |
|-------------------------------------|--------------------|-----------|-----------|-----------------|
| HistGradientBoostingRegressor       | 0.88               | 0.88      | 129600.41 | 0.71            |
| LGBMRegressor                       | 0.87               | 0.87      | 134150.78 | 0.39            |
| XGBRegressor                        | 0.87               | 0.87      | 136435.61 | 0.55            |
| ... (Top models)                    | ...                | ...       | ...       | ...             |


5. ***Conclusion***

- The models were evaluated using LazyRegressor to compare their performance on two different paths.
- Path 1: All columns included.
- Path 2: Removed some columns with low PCA to reduce complexity.

- **Top 5 Models (Path 1):**
    1. HistGradientBoostingRegressor
    2. XGBRegressor
    3. LGBMRegressor
    4. GradientBoostingRegressor
    5. RandomForestRegressor

- **Top 5 Models (Path 2):**
    1. HistGradientBoostingRegressor
    2. LGBMRegressor
    3. XGBRegressor
    4. RandomForestRegressor
    5. BaggingRegressor
    
    
   **Key Findings:**
   - The model performances between Path 1 and Path 2 are comparable.
   - Path 2, with reduced columns, exhibits reduced time complexity (In some models).
