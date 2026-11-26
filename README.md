# Airbnb Data Cleaning

Cleaning the Airbnb Open Data dataset (NYC) with pandas.

## Dataset
Airbnb Open Data from Kaggle (`arianazmoudeh/airbnbopendata`): 102,599 rows and 26 columns at the start.

## What I did
- Removed 541 duplicate rows
- Fixed typos in neighbourhood group (`brookln`, `manhatan`)
- Filled missing locations using a neighbourhood-to-group lookup
- Filled coin-flip categories (host verified, instant bookable, cancellation policy) with `unknown` instead of mode
- Converted `PRICE` and `SERVICE FEE` from text (`$966`) to numbers
- Filled missing `SERVICE FEE` as 20% of price (checked: ratio std 0.001)
- Dropped rows with missing `PRICE`, because price is the likely prediction target
- Treated impossible `MINIMUM NIGHTS` values (below 1 or above 365) as errors and filled them with the median
- Dropped rows with missing coordinates

## Result
101,163 rows and 18 columns, with no missing values and no duplicates.

## Notes
- Prices are evenly spread from 50 to 1,200 and fees are almost exactly 20% of price, so the data may be synthetic.
- The cleaned CSV is not uploaded. Run the notebook to recreate it.

## Tools
Python, pandas, Jupyter Notebook