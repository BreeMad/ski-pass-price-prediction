# Data Instructions

## Source

- **Dataset:** [Maven Analytics’ Ski Resorts Dataset](https://mavenanalytics.io/data-playground/ski-resorts).
- **Original sources credited by Maven for the collection:** Ski-resort-stats.com and NASA Earth Observations.
- **File used:** `resorts.csv`. The separate snow-cover dataset is not used.

## Data Used in This Project

The notebook starts with **499 ski resorts and 24 data column**s. Each ski resort’s `ID` is used as its row label.

The notebook reads `resorts.csv` from its working folder, usually `/content` in Google Colab. It uses these settings:

- `encoding='latin-1'`: Allows the notebook to read special characters in the file.
- `index_col='ID'`: Uses the ski resort IDs as row labels.

The prices are for one-day adult ski passes and are listed in euros.

## How to Download and Use the Data

1. Open the Maven Analytics link above and download the dataset. You may need to sign in.
2. Unzip the download and find `resorts.csv`.
3. Open `ski_pass_price_prediction.ipynb` in Google Colab. Use the **Files** panel to upload `resorts.csv` to the `/content` folder.
4. Keep the filename the same and run the notebook cells from top to bottom. See the [README](README.md#how-to-run-in-google-colab) for package setup.

The CSV file is not included in this repository. Download resorts.csv from the Maven Analytics link above. If the dataset has been updated, your results may differ from the saved results.
