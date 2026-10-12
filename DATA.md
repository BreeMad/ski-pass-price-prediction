# Data instructions

## Source

- **Dataset:** Ski Resorts.
- **Downloaded from:** [Maven Analytics Data Playground](https://mavenanalytics.io/data-playground/ski-resorts).
- **Original sources listed by Maven for the dataset collection:** Ski-resort-stats.com and NASA Earth Observations.

Maven's dataset collection includes resort information and a separate snow-cover table. This project uses `resorts.csv`; it does not use the companion snow-cover table.

## Input used in this project

The notebook starts with 499 resorts and 24 data columns after `ID` is set as the index. The input is `resorts.csv`, read from the notebook's working folder with `encoding='latin-1'` and `index_col='ID'`. Prices represent one-day adult ski passes in euros, as described in the notebook.

## How to obtain and use the data

1. Open the Maven Analytics dataset link above and download the Ski Resorts dataset. Maven may require you to sign in.
2. Unzip the download and locate `resorts.csv`.
3. Open `ski_pass_price_prediction.ipynb` in Google Colab and upload the CSV through the Files panel to the working folder, normally `/content`.
4. Keep the CSV filename unchanged and run the notebook cells in order.

The original CSV is not included in this package. Use the original file used for this analysis where possible, because future source revisions may affect results. No specific dataset version or original download date is recorded.
