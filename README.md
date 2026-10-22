# ⚡ Energy Consumption Forecasting System

An interactive machine learning application that analyzes historical electricity consumption, compares forecasting models, and predicts future daily energy usage using Python and Streamlit.

## 📌 Project Overview

The **Energy Consumption Forecasting System** helps users understand electricity usage patterns and forecast future energy consumption using historical data.

Users can upload their own energy consumption dataset in CSV format, explore interactive visualizations, evaluate forecasting models using chronological backtesting, and download forecast results.

The application currently supports built-in synthetic sample data for demonstration. Real-world performance must be evaluated using actual energy consumption data.

## 🎯 Objectives

- Analyze historical electricity consumption.
- Identify daily and weekly consumption patterns.
- Forecast future electricity usage.
- Compare multiple machine learning models.
- Evaluate forecasting accuracy using time-aware testing.
- Visualize actual versus predicted energy consumption.
- Allow users to download cleaned data and forecast results.
- Work toward reducing forecasting error compared with a baseline model.

## ✨ Features

- **CSV Upload:** Upload energy consumption data.
- **Data Validation:** Check the input data and report data quality issues.
- **Historical Analysis:** Visualize daily energy consumption.
- **Usage Pattern Analysis:** Compare average consumption by day of the week.
- **Multiple Forecasting Models:** Compare different forecasting approaches.
- **Chronological Evaluation:** Train on earlier observations and evaluate on later observations.
- **Model Comparison:** Compare forecasting errors against a baseline.
- **Future Forecasting:** Predict daily energy consumption for a configurable forecast horizon.
- **Interactive Dashboard:** Explore results through Streamlit and Plotly.
- **CSV Export:** Download cleaned data and future forecasts.

## 🛠️ Technologies Used

- Python
- Streamlit
- Pandas
- NumPy
- Scikit-learn
- Plotly

## 🤖 Forecasting Models

The application currently supports the following models:

1. **Seasonal Naive (7-day):** Uses previous observations from the same weekday as a baseline.
2. **Linear Regression:** Learns relationships between time-related features, historical consumption, and energy usage.
3. **Random Forest Regressor:** Combines predictions from multiple decision trees.
4. **Gradient Boosting:** Uses a boosting-based regression model to learn patterns in energy consumption.

Models are compared using chronological evaluation so that future observations are not randomly mixed into the training data.

## 📊 Evaluation Metrics

The application uses three common regression metrics:

| Metric | Description |
|---|---|
| MAE | Mean Absolute Error; average absolute prediction error in kWh. |
| RMSE | Root Mean Squared Error; gives greater weight to larger errors. |
| MAPE | Mean Absolute Percentage Error; average absolute error expressed as a percentage. |

### Baseline Error Reduction

The percentage reduction in MAE is calculated as:

`MAE Reduction (%) = ((Baseline MAE - Model MAE) / Baseline MAE) × 100`

A positive result means the model performs better than the baseline on the evaluated data.

**Project target:** Aim for a 95% reduction in forecasting error compared with the baseline. This is a target, not a guaranteed result. The model must achieve it on valid evaluation data before claiming success.

## 📁 Project Structure

```text
EnergyConsumptionForecasting/
│
├── app.py
├── src/
│   ├── __init__.py
│   ├── data_processing.py
│   └── forecasting.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

Your actual project may contain additional files or folders. Keep your existing working files and reflect the real structure in this section before publishing.

## ⚙️ Installation and Setup

### Prerequisites

- Python 3.10 or a compatible version for your installed dependencies
- pip
- Git (optional, for GitHub upload)

### 1. Download or Clone the Project

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd EnergyConsumptionForecasting
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your actual repository URL. If you already have the project locally, open its existing folder instead.

### 2. Install Dependencies

Use your existing Python environment; creating a separate environment is not required.

```bash
pip install -r requirements.txt
```

### 3. Run the Application

```bash
streamlit run app.py
```

Streamlit will display a local URL, usually:

```text
http://localhost:8501
```

Open that URL in your browser.

## 📄 Dataset Format

The application expects a CSV containing these required columns:

| Column | Description | Example |
|---|---|---|
| `Date` | Date of the observation | `2025-01-01` |
| `Energy_Consumption` | Energy consumed during that day, in kWh | `125.4` |

Example CSV format:

```csv
Date,Energy_Consumption
2025-01-01,125.4
2025-01-02,131.2
2025-01-03,119.8
```

The values above are illustrative examples, not measured results.

The dataset should contain valid dates, numeric energy consumption values, and sufficient historical observations. Hourly readings must be converted to daily consumption before using them as daily totals.

## 🚀 How to Use

1. Start the Streamlit application.
2. Upload a CSV file or enable the built-in sample data option.
3. Review the data quality report.
4. Explore the historical consumption chart.
5. Analyze average electricity usage by weekday.
6. Select a forecasting model from the sidebar.
7. Set the forecast horizon.
8. Review MAE, RMSE, and MAPE.
9. Compare models using chronological backtesting.
10. View the future energy consumption forecast.
11. Download the forecast or cleaned dataset as a CSV file.

## 📈 Current Development Status

- [x] Streamlit dashboard
- [x] CSV upload interface
- [x] Built-in synthetic sample data
- [x] Data validation and cleaning
- [x] Historical consumption visualization
- [x] Day-of-week consumption analysis
- [x] Multiple forecasting models
- [x] Chronological model evaluation
- [x] Baseline error reduction comparison
- [x] Forecast visualization and CSV downloads
- [ ] Validation on a real-world energy dataset
- [ ] Further model tuning and feature engineering
- [ ] Verification of the 95% error-reduction target on unseen data

## 🔮 Future Enhancements

- Integrate real-world electricity consumption datasets.
- Incorporate weather conditions, holidays, and calendar features.
- Add more forecasting algorithms.
- Improve performance through systematic hyperparameter tuning.
- Support hourly, daily, and monthly forecasting.
- Add additional validation windows and error analysis.
- Deploy the application to a cloud platform.

## ⚠️ Limitations

- Forecast quality depends on the dataset and its historical patterns.
- Synthetic data is useful for demonstrating functionality but does not establish real-world accuracy.
- Unexpected weather, equipment changes, holidays, and changes in user behavior can affect energy demand.
- Forecasts are estimates, not guarantees.
- The 95% reduction target has not been verified unless confirmed through actual evaluation results.

## 👩‍💻 Author

**Elakkiya Selvi S M**

AI and Data Science Project

## 📜 License

This project can be published under the MIT License if you choose to distribute it under those terms. Add a `LICENSE` file before claiming that the repository is MIT-licensed.

## 🙌 Acknowledgements

- Streamlit for the interactive application framework.
- Scikit-learn for machine learning algorithms and evaluation tools.
- Pandas and NumPy for data processing.
- Plotly for interactive visualizations.
- UCI Machine Learning Repository for potential real-world energy dataset sources.
