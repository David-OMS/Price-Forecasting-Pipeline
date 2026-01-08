# Price-Forecasting-Pipeline

End-to-end data pipeline for collecting, processing, and analyzing food ingredient prices in Nigeria. Includes ML model testing to see if predictions beat simple baselines.

## What This Does

Collects food price data from multiple sources, cleans and integrates it, then tests whether machine learning models can predict future prices better than just using last month's price.

## Findings

- For Milk and Sugar, which showed low month-to-month variability in this dataset, simple baseline predictions performed as well as or better than the ML models tested.

- For Banana, ML and baseline predictions were roughly comparable.

- Sparse or irregular data (Culture imports) limited predictive performance for all approaches.After building ML models and testing them properly:


**Takeaway**: 

- In datasets with limited observations or low variability, simple baseline methods can perform as well as ML models.

- ML may show greater value if richer datasets, higher-frequency observations, or additional external signals are available.

- The project demonstrates a reliable workflow for collecting, cleaning, and integrating multiple data sources, creating a foundation for future predictive modeling.

## Tech Stack

- Python, Pandas, NumPy for data processing
- scikit-learn, XGBoost for ML models
- Matplotlib, Seaborn for visualization
- Jupyter for analysis

## Quick Start

### Prerequisites
- Python 3.7+
- pip

### Installation

```bash
# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### View Analysis

```bash
# Start Jupyter Notebook
jupyter notebook
```

Open `analysis.ipynb` to see:
- Data collection and sources
- Data transformation and feature engineering
- Model training and evaluation
- Baseline comparison results

## Project Structure

```
├── data/
│   ├── raw/              # Raw source data
│   └── processed/        # Processed data 
├── analysis.ipynb        # Main analysis notebook
├── requirements.txt      # Python dependencies
└── README.md            # This file
```

## Data Sources

### Core Food Price Data
- **WFP (World Food Programme)**: Retail food prices for Nigeria (Milk, Bananas, Sugar)
- **UN Comtrade**: Starter culture import data (bacteria for yogurt production)

### External Signals
- **Fuel Prices**: NBS official rates (PMS/Petrol, AGO/Diesel) - collected via web scraping
- **Forex Rates**calculated from WFP data
- **Inflation**: NBS CPI data - collected via web scraping

## Output

The pipeline generates:
- **Integrated Dataset** (`data/integrated_food_prices.csv`): Monthly prices (2022-2025) for all ingredients in NGN and USD, plus external signals
- **Analysis Results**: Comparison of ML models vs simple baseline for each commodity

## Documentation

- **This README**: Project overview and quick start
- **`analysis.ipynb`**: Complete data processing, transformation, and model evaluation workflow
