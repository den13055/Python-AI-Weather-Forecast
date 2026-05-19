##🌦️ Optimal weather forecast based on open-source data

Course project on "Problem Solving Models in Intelligent Systems"
A machine learning model based on **ridge regression** was developed for forecasting weather parameters (temperature) based on historical data from 1973 to 2023.

## 🧠 Methods Used

- **Linear Regression** – a basic forecasting method
- **Ridge Regression** – to combat multicollinearity and overfitting
- Data Processing: `pandas`, `NaN` removal, time series shifting to create a target variable

## 🛠️ Technologies and Tools

- **Programming Language:** Python 3
- **Runtime Environment:** Google Colab
- **Libraries:**
- `pandas` – data loading and processing
- `scikit-learn` – Ridge model, sample splitting
- `google.colab` – Google Drive connection
- **Data Source:** NOAA (National Centers for Environmental Information) – data from airports worldwide

## 📁 Structure Project

```
├── Weather.ipynb # Jupyter Notebook / Colab with the model implementation
└── README.md # Project Description
```

## ⚙️ Main Stages of the Work

### 1. Loading and Preparing Data
- Data is read from a CSV file (hosted on Google Drive)
- Columns with >30% missing values ​​(`SNOW`, `SNWD`) are removed
- Empty values ​​are filled using the `ffill` method (previous value)
- The date is converted to `datetime` format

### 2. Creating the Target Variable
The `target` column is created by shifting the time series – the temperature value for the next day is predicted.

### 3. Model Training
- Using `Ridge(alpha=0.1)`
- Data is split into training (first 3650 days) and test sets in 30-day increments
- Estimated average absolute error (difference)

### 4. Result
The model shows an average error of 3.31°F (about 1.8°C) in predicting the maximum temperature.

## 📊 Example Output

| actual | prediction | diff |
|--------|------------|---------|
| 65.4 | 64.1 | 1.3 |
| 70.2 | 71.5 | 1.3 |
| ... | ... | ... |

## 🚀 How to run the project

1. **Clone the repository**
```bash
git clone https://github.com/your-username/weather-forecast-ml.git
cd weather-forecast-ml
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Open the notebook in Google Colab or Jupyter**
- Upload the `Weather.csv` file to Google Drive
- Specify the correct path to the file
- Run all cells

## 📄 License

MIT License
