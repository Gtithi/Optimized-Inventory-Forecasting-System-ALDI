# 📦 Data Directory

This folder contains (or expects) the input datasets used for training and evaluating the inventory forecasting models.

## 📁 Expected Files:

- `sales.csv` — Historical daily product sales
- `inventory.csv` — Daily closing inventory levels per product
- `delivery.csv` — Delivery records to stores (quantity, date)
- `writeoffs.csv` — Write-offs due to spoilage/damage
- `forecast.csv` — Internal demand forecast made by Aldi Süd

Each file should contain at least the following:
- A `date` column in `YYYY-MM-DD` format
- A `product_id` and/or `store_id` column
- Relevant numeric values (e.g., quantity, inventory level)

---

## 🔒 Data Privacy Disclaimer

These datasets were shared under NDA for academic purposes as part of a collaboration with Aldi Süd.  
**The raw data is NOT included in this repository due to confidentiality.**

If you're reproducing this project, please use:
- Synthetic datasets with similar structure, OR
- Public retail datasets available on platforms like Kaggle.

---

## 🛠️ Data Integration Note

All datasets are joined by:
- `date`
- `store_id`
- `product_id`

After merging, any missing values in numerical columns (sales, delivery, writeoffs) are filled with `0`.  
Inventory values are forward-filled under business logic constraints.
