# Stock Price Prediction Using Machine Learning

A beginner-friendly machine learning project for exploring historical stock prices and building a model that predicts a future closing price from historical market data.

> **Disclaimer:** This project is for educational purposes only. Predictions are estimates, not financial advice. Stock prices are uncertain, and this project should not be used as the sole basis for investment decisions.

## Features

- Load historical stock data from a CSV file
- Validate and prepare date and price columns
- Explore closing-price history with a chart
- Train a baseline regression model
- Evaluate predictions with MAE, RMSE, and R²
- Save a plot of actual versus predicted values

## Project structure

```text
stock-price-prediction-using-machine-learning/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── data/
│   └── README.md
├── notebooks/
│   └── stock_price_prediction.ipynb
├── src/
│   ├── __init__.py
│   └── train.py
├── outputs/
│   └── .gitkeep
└── tests/
    └── test_data.py
```

## Requirements

- Python 3.10 or newer
- Historical stock data in CSV format

## Setup

### 1. Extract the ZIP file

Extract this folder to a location on your computer.

### 2. Create a virtual environment (recommended)

Windows:

```bash
python -m venv .venv
.venv\\Scripts\\activate
```

macOS/Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Prepare your data

Place a CSV file at `data/stock_data.csv`. The CSV must contain:

- `Date` — date of the observation
- `Close` — closing price

Optional columns such as `Open`, `High`, `Low`, and `Volume` may also be included. Use data you are permitted to access and redistribute, and check the source's terms.

Example:

```csv
Date,Open,High,Low,Close,Volume
2025-01-02,100,105,99,103,120000
2025-01-03,103,107,102,106,135000
2025-01-06,106,108,104,105,110000
```

The sample above is illustrative only, not real market data.

## Run the project

From the project root:

```bash
python -m src.train --input data/stock_data.csv
```

To choose an output directory:

```bash
python -m src.train --input data/stock_data.csv --output outputs
```

The script creates:
- `outputs/predictions.csv`
- `outputs/actual_vs_predicted.png`

It uses chronological splitting so the model is evaluated on later observations than those used for training. The included model is a simple baseline using lagged closing prices and should not be interpreted as a reliable market forecast.

## Run tests

```bash
python -m unittest discover -s tests
```

## Upload to GitHub

1. Sign in to GitHub and create a new repository, for example `stock-price-prediction-using-machine-learning`.
2. Extract this ZIP file.
3. Open the extracted project folder.
4. Upload the files and folders to your repository, or use Git:

```bash
git init
git add .
git commit -m "Initial project structure"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/stock-price-prediction-using-machine-learning.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username. If you use GitHub's web interface, upload the folder contents rather than the ZIP file itself.

## Limitations

- Historical patterns do not guarantee future results.
- The baseline model uses only prior closing prices.
- Transaction costs, market events, and broader economic factors are not modeled.
- Model quality depends on data quality and the selected evaluation period.

## License

This project is released under the MIT License. See [LICENSE](LICENSE).
