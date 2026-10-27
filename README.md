# E-Waste Recycling Analysis

Cleans and analyses a dataset of 1,529 e-waste records to understand what affects the resale value of recycled electronics and how they are processed.

Module: ANL252 Python for Data Analytics, Singapore University of Social Sciences (2026). Group project.

## Approach

1. **Load and inspect** the dataset: 1,529 rows and 16 columns covering item type, condition, recycling method, location and recycled price.
2. **Find missing values:** `Toxic_Components` (370), `Recycle_Method` (158), `Recycled_Price_USD` (140) and `Year_of_Purchase` (2).
3. **Treat missing values** based on the type of variable and how much is missing:
   - Numeric fields: median imputation, which is less affected by extreme values than the mean.
   - `Recycle_Method` (10% missing): mode imputation.
   - `Toxic_Components` (24% missing): a new `Unknown` category, so the distribution is not distorted.
4. **Analyse and visualise** with pandas `groupby` and matplotlib.

## Key findings

**Average recycled price (USD) by category and condition**

| Category | Broken | Partially Working | Working |
|---|---|---|---|
| Appliance | 96.41 | 93.27 | 107.41 |
| Laptop | 113.32 | 110.59 | 105.54 |
| Mobile | 99.42 | 104.21 | 104.25 |
| TV | 104.22 | 100.87 | 98.77 |

- Laptops keep the most value even when broken, which suggests the value is in recoverable parts such as RAM and processors.
- The type of device affects recycled value more than its condition does.
- Manual processing is the most common method in every category, so recycling still relies heavily on human labour.
- Recycled prices rose and fell from year to year with no clear trend, which points to market factors rather than device age.

## How to run

```bash
pip install pandas matplotlib jupyter
jupyter notebook e_waste_analysis.ipynb
```

The notebook expects `GBA_waste.csv` in the same folder. The dataset was provided for coursework and is not included here.

## Skills demonstrated

- Handling missing data with pandas
- Grouped aggregation and pivoting
- Bar and line charts with matplotlib
- Interpreting results in their business and environmental context

## Author

Jawenn Lim
