# Data Instructions

## Data Source

This project uses the [Ski Resorts Dataset from Maven Analytics](https://mavenanalytics.io/data-playground/ski-resorts).

Maven Analytics lists Ski-resort-stats.com and NASA Earth Observations as sources for the dataset.

I used the **`resorts.csv`** file. The separate snow-cover dataset was not used.

## Data Used in This Project

The original dataset contains **499 ski resorts and 24 columns**. Each resort has its own ID, which is used as its row label.

The prices are listed in euros and are for **one-day adult ski passes**.

I removed 9 resorts with €0 ski pass prices, leaving **490 resorts**. I used 392 resorts for training and set aside 98 for final testing.

The notebook reads the CSV file using these settings:

- **`encoding="latin-1"`:** Helps Python read special characters in the file.
- **`index_col="ID"`:** Uses each resort's ID as its row label.

## How to Download and Use the Data

1. Open the [Maven Analytics Ski Resorts Dataset](https://mavenanalytics.io/data-playground/ski-resorts) and download it. You may need to sign in.
2. Unzip the downloaded folder and find **`resorts.csv`**.
3. Open **`ski_pass_price_prediction.ipynb`** in Google Colab.
4. Use Colab's **Files** panel to upload `resorts.csv` to the `/content` folder.
5. Keep the filename the same and run the notebook cells from top to bottom.

See the `README.md` file for help setting up the Python packages.

**Note:** The CSV file is not included in this GitHub repository. You will need to download it from Maven Analytics.

If the dataset changes in the future, your results may be different from the results saved in this project.
