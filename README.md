# Ski Pass Price Prediction

Estimating the price of a one-day adult ski pass using resort terrain, location, season, and available features.

**Project type:** Regression | **Tools:** Python, Pandas, NumPy, statsmodels, SciPy, scikit-learn, Matplotlib, Seaborn

## Main result

Ridge regression was selected as the final model. Its predictions were off by about **€9.29 on average** in the test data.

| Test metric | Result |
| --- | ---: |
| R-squared | 0.568 |
| Mean absolute error (MAE) | €9.287 |
| Root mean squared error (RMSE) | €12.131 |

R-squared describes how much of the price variation the model explains. MAE describes the average size of a prediction error. RMSE gives larger mistakes more weight.

![Ski pass price, difficult slopes, and continent](images/price_terrain_continent.png)

This chart is an exploratory view of the data, rather than the final model's prediction results.

## Business question

How well can resort features estimate ski pass prices and support comparisons between resorts?

## Data Source

This project uses the [Ski Resorts dataset from Maven Analytics](https://mavenanalytics.io/data-playground/ski-resorts), which includes resort locations, prices, slopes, lifts, and seasons for roughly 500 ski resorts around the world.

The analysis uses `resorts.csv`. The companion snow-cover table is not used in this project.

## Data and workflow

- Used the Maven Analytics Ski Resorts dataset, starting with 499 resorts and 24 data columns, with `ID` stored as the index.
- Inspected data types, distributions, unusual prices, and relationships between features.
- Built linear regression models and examined residuals and overlapping predictors.
- Explored combined features and categorical information such as continent and season.
- Compared linear models with Ridge and Lasso regression.
- Used cross-validation and an 80/20 train-test split for model assessment.

## Final model comparison

| Model | Test R-squared | Test MAE (€) | Test RMSE (€) |
| --- | ---: | ---: | ---: |
| Refined linear model | 0.230 | 11.580 | 16.189 |
| Interaction model | 0.501 | 10.172 | 13.028 |
| Categorical model | 0.559 | 9.423 | 12.250 |
| Ridge | 0.568 | 9.287 | 12.131 |
| Lasso | 0.560 | 9.377 | 12.232 |

## Key findings

Adding categorical information improved test performance compared with the refined numeric model. Ridge performed best among the final models compared, although substantial prediction errors remained.

The model could provide a starting point for price estimates. More information about demand, popularity, snowfall, holidays, and nearby competition could improve it.

## Files

- [Full notebook](ski_pass_price_prediction.ipynb): code, explanations, charts, and saved results.
- [Data instructions](DATA.md): source and required CSV.
- `requirements.txt`: Python package requirements for reference or installation if needed.
- `images/`: a chart taken from the notebook's saved outputs.

## How to run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/) and upload `ski_pass_price_prediction.ipynb` using **File > Upload notebook**.
2. Obtain the original `resorts.csv` described in [DATA.md](DATA.md).
3. Upload the CSV through Colab's **Files** panel. Keep its filename unchanged and place it in the runtime's working folder, normally `/content`, because the notebook reads it using a relative filename.
4. Run the notebook cells in order.

Colab provides the notebook environment, so you do not need to install or start Jupyter on your computer. If a required package is missing or incompatible, upload `requirements.txt` to the runtime's working folder and run `%pip install -r requirements.txt` in a new code cell before the analysis. Restart the runtime if prompted after package changes, then rerun the notebook from the start. The requirements are not a fully verified environment lock.

Uploaded CSVs belong to the temporary runtime. You may need to upload them again when starting a new session.

You can also read the saved notebook results on GitHub without downloading the data or running the models.

## Limits and next steps

The data covers a limited number of resorts. Missing demand and business information may explain part of the remaining prediction error. Relationships in this dataset do not prove what causes higher prices.

The final model was chosen through test-set comparisons. A future evaluation should use training-only model selection, put scaling inside cross-validation, and reserve a fresh holdout dataset for the final assessment.

The repository preserves the supplied analysis and saved results. The notebook's data-source section now includes the confirmed dataset link. Full execution was not repeated while preparing this repository because the original CSV was not supplied. Package versions are starting requirements rather than a fully verified environment lock.
