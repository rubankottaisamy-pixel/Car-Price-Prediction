# Car-Price-Prediction
Car Price Prediction Project
# 🚗 Car Price Prediction

A machine learning project to predict the **selling price of used cars** based on features like manufacturing year, fuel type, transmission, kilometers driven, and more.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Models & Results](#models--results)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Used car pricing is influenced by a range of factors — age, mileage, fuel type, seller type, and more. This project builds a regression model to predict the **selling price (in lakhs INR)** of a used car given its attributes, helping buyers and sellers make informed decisions.

---

## Dataset

The dataset (`cardata.csv`) contains **301 records** of used cars with **9 features**:

| Column | Description |
|---|---|
| `Car_Name` | Name/model of the car |
| `Year` | Year of manufacture (2003–2018) |
| `Selling_Price` | Price at which the car was sold (target variable, in lakhs) |
| `Present_Price` | Current ex-showroom price of the car (in lakhs) |
| `Kms_Driven` | Total kilometers driven |
| `Fuel_Type` | Fuel type — Petrol, Diesel, or CNG |
| `Seller_Type` | Dealer or Individual |
| `Transmission` | Manual or Automatic |
| `Owner` | Number of previous owners |

### Key Stats
- **Rows:** 301 | **Columns:** 9 | **Missing values:** None
- **Selling Price range:** ₹0.1L – ₹35L
- **Fuel types:** Petrol (79%), Diesel (20%), CNG (1%)
- **Transmission:** Manual (87%), Automatic (13%)

---

## Features

- **Exploratory Data Analysis (EDA)** — distributions, correlations, and outlier detection
- **Feature Engineering** — car age derived from year, label/one-hot encoding of categorical variables
- **Multiple ML Models** — Linear Regression, Random Forest, Gradient Boosting, etc.
- **Model Evaluation** — R², MAE, RMSE comparison across models
- **Prediction Pipeline** — end-to-end pipeline for new car price predictions

---

## Project Structure

```
car-price-prediction/
│
├── data/
│   └── cardata.csv          # Raw dataset
│
├── notebooks/
│   └── EDA.ipynb            # Exploratory data analysis
│   └── Modeling.ipynb       # Model training & evaluation
│
├── src/
│   ├── preprocess.py        # Data cleaning & feature engineering
│   ├── train.py             # Model training script
│   └── predict.py           # Inference / prediction script
│
├── models/
│   └── car_price_model.pkl  # Saved trained model
│
├── requirements.txt
└── README.md
```

---

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/car-price-prediction.git
   cd car-price-prediction
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

### Train the model
```bash
python src/train.py --data data/cardata.csv --model models/car_price_model.pkl
```

### Predict on new data
```bash
python src/predict.py \
  --model models/car_price_model.pkl \
  --year 2015 \
  --present_price 7.5 \
  --kms_driven 45000 \
  --fuel_type Petrol \
  --seller_type Dealer \
  --transmission Manual \
  --owner 0
```

### Run Jupyter Notebooks
```bash
jupyter notebook notebooks/
```

---

## Models & Results

| Model | R² Score | MAE | RMSE |
|---|---|---|---|
| Linear Regression | ~0.85 | ~1.2 | ~1.8 |
| Random Forest | ~0.96 | ~0.5 | ~0.9 |
| Gradient Boosting | ~0.97 | ~0.4 | ~0.8 |

> Results are approximate and may vary with hyperparameter tuning and train/test split.

---

## Requirements

```
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
```

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

<p align="center">Made with ❤️ for data science enthusiasts</p>
