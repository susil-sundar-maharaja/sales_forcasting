# Sales Forecasting

A course-end capstone project that analyses three years of daily item sales across six restaurants and forecasts total daily sales for the next year.

## Project files

- `work.ipynb` – the full analysis: data checks, merging, EDA and forecasting
- `sales.csv` – daily item count and price for each item (109,600 rows, 2019–2021)
- `items.csv` – item details: store, name, calories and cost (100 items)
- `resturants.csv` – restaurant ids and names (6 restaurants)
- `project_writeup.docx` – detailed write-up of the findings and results
- `requirements.txt` – Python packages used

## How to run

1. Create and activate a virtual environment:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

2. Install the packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Open `work.ipynb` in Jupyter or VS Code, select the environment as the kernel, and run all cells from top to bottom. The CSV files need to be in the same folder as the notebook.

## What the notebook does

1. Loads the three datasets and checks their shape, missing values, duplicates and outliers
2. Merges them into one table with date, item, price, item count, calories and store name
3. Explores sales by day of the week, month, quarter, restaurant and item
4. Builds date features and compares Linear Regression, Random Forest and XGBoost, using the last six months as test data
5. Retrains the best model on all data and forecasts daily sales for 2022

## Results

| Model | RMSE (test, last 6 months) |
|---|---|
| Linear Regression | 244.2 |
| Random Forest | 62.5 |
| XGBoost | 60.7 |

XGBoost was chosen as the final model. Sales peak in June and July and on Fridays and Saturdays. Bob's Diner accounts for almost all of the volume, and Strawberry Smoothy is the best-selling item.

See `project_writeup.docx` for the full explanation.
