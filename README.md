Optimized Inventory Forecasting System – ALDI Süd

This project implements a short-term inventory forecasting system using machine learning models (XGBoost and LSTM) on real-world retail data from Aldi Süd Austria. The goal is to predict the inventory level for a selected product over a 7-day horizon to enhance operational efficiency and reduce stockouts or overstocking.

📌 Project Objective

Predict next 7 days of inventory levels for a single product in Aldi Süd outlets.

Compare the performance of LSTM (neural networks for sequence modeling) and XGBoost (tree-based regression).

Deliver actionable insights to improve demand planning and stock control.

📊 Dataset Description

Data provided by Aldi Süd includes:

sales.csv — Historical daily product sales (units/weight)

inventory.csv — Daily closing inventory levels

delivery.csv — Product delivery records to stores

writeoffs.csv — Write-offs due to spoilage/damage

forecast.csv — Aldi’s internal demand forecast

Period: January 2023 – June 2024Stores: 3 outletsProducts: 90 (only 1 selected for final modeling)

🧪 Methodology

Models Considered

ARIMA (Rejected early due to weak performance)

Prophet (Not used further)

XGBoost: Gradient-boosted trees, fast but weak with sequential patterns

✅ LSTM: Chosen for final forecasting due to superior handling of temporal dependencies

Model Process

Data cleaning & merging

Feature creation & sequence preparation

Train/test split

Hyperparameter tuning

Forecast generation

Performance evaluation using MAE, MSE, R²

Visual comparison of actual vs predicted inventory

📊 Results

Metric

LSTM (Final Model)

XGBoost (Baseline)

MAE

17.6

3.97

MSE

28.6

94.05

R²

∼ Not reported

0.93

LSTM captured short-term trends effectively (1–3 days).

Forecast degraded slightly for days 4–7, common in sequence modeling.

XGBoost did well with lag features but lacked sequential memory.

⚠️ Note: LSTM was chosen for robustness despite slightly higher MAE, due to better generalization and adaptability.

📂 Folder Structure

Optimized-Inventory-Forecasting-System-ALDI/
├── aldi_forecasting.ipynb           # Cleaned notebook (rename from Untitled1)
├── README.md                        # This documentation
├── requirements.txt                 # Python dependencies
├── report/                          # Final PDF report (optional)
│   └── final_project_report.pdf     
├── data/                            # Data files or schema (placeholders)
│   └── README.md (data handling policy)
├── models/                          # Saved LSTM/XGBoost models (optional)
│   └── lstm_model.h5 / xgb_model.json
├── figures/                         # Forecasting plots, metrics, etc.
│   └── inventory_forecast.png
└── LICENSE                          # MIT or academic license

⚙️ Setup & Installation

📦 Dependencies

Install all required packages:

pip install -r requirements.txt

Or set up a virtual environment:

python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
pip install -r requirements.txt

▶️ How to Run

Clone this repo:

git clone https://github.com/Gtithi/Optimized-Inventory-Forecasting-System-ALDI.git
cd Optimized-Inventory-Forecasting-System-ALDI

Open the Jupyter notebook:

jupyter notebook aldi_forecasting.ipynb

Or run in Google Colab directly by uploading it.

Step through the notebook sections:

Data preparation

Model training

Forecasting and visualization

Result evaluation

📷 Visualizations

All key plots are saved under /figures:

inventory_forecast.png — LSTM forecast vs. actual inventory

loss_curve.png — Model training loss progression

xgb_comparison.png — XGBoost prediction visualization

📚 References

Akanksha et al. (2022), ICICT: Store-Sales Forecasting

Jean-Claude Munyaka et al. (2022): Inventory Management Review

RWTH Aachen course material (Chair of Data & Business Analytics)

👥 Authors

Tithi Ghosh – @Gtithi

Mainak Dasgupta

Ritesh Radhakrishnan

Supervised by: Prof. Dr. Sven Müller (RWTH), Florian Hahn (Aldi Süd), Sarah Woldrich (Aldi Süd)

📄 License

This repository is open-sourced under the MIT License. See LICENSE for more details.
