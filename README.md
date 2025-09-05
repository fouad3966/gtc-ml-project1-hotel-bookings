# GTC ML Project 1 - Hotel Bookings

This repository contains a Colab-ready notebook and dataset for Project 1.

Deliverables:
- `GTC_ML_Project1_Hotel_Bookings.ipynb` 
- `hotel_bookings.csv` — original dataset
- `hotel_bookings_train_clean.csv`, `hotel_bookings_test_clean.csv` — cleaned outputs produced by the notebook
- `preprocessor.pkl` — pickled preprocessing pipeline

## How to run
1. Open the notebook in Google Colab.
2. Upload `hotel_bookings.csv` when requested.
3. Run all cells sequentially.

## Data cleaning decisions summary
- Dropped `reservation_status` & `reservation_status_date` to prevent leakage (they contain post-fact booking outcomes).
- `company` missing values replaced with `'None'` (string).
- `agent` missing values replaced with `0` (treated as no agent).
- `country` missing values imputed with mode.
- `children` missing values imputed with median if any present.
- Capped `adr` at 1000 to reduce extreme-value skew.
- Created features: `total_guests`, `total_nights`, `is_family`.
- For high-cardinality country feature: grouped rare countries (<1% frequency) into `Other` and frequency-encoded the grouped value.
