# Bitcoin Price Prediction Using Machine Learning

## Project Overview

This project aims to predict the price movement of Bitcoin (BTC-USD) using historical data obtained from Yahoo Finance and machine learning techniques. The primary objective is to forecast whether the price will go up or down the next day.

## Data Source

The historical data for Bitcoin is sourced from Yahoo Finance.

## Files

- `BTC_USD_price_prediction.ipynb`: The main Python script containing the entire process of data loading, cleaning, feature engineering, model training, and evaluation.
- `README.md`: This readme file, provides an overview of the project and instructions for setup and usage.

## Dependencies

The project uses the following Python packages:

- yfinance
- pandas
- scikit-learn
- matplotlib

You can install the required packages using the following command:

```sh
pip install yfinance pandas scikit-learn matplotlib
```

## Data Preparation

1. **Loading Data**: The historical data is loaded from Yahoo Finance.
2. **Cleaning Data**: Unnecessary columns (`Dividends` and `Stock Splits`) are removed.
3. **Feature Engineering**:
   - A new column `Tomorrow` is added to store the next day's closing price.
   - A target column `Target` is created, which indicates if the next day's price will be higher (`1`) or lower (`0`) than the current day's price.
   - Additional predictors are created using rolling averages to capture trends over different horizons.

## Model Training

A Random Forest Classifier is used for the prediction task. The model is trained using the following steps:

1. **Initial Model**: A basic Random Forest model is trained and evaluated.
2. **Backtesting**: A backtesting approach is implemented to evaluate the model's performance over time, training on past data and predicting future data.
3. **Feature Enhancement**: Rolling averages and trend indicators are added as additional predictors to improve model performance.

## Model Evaluation

The model's performance is evaluated using the precision score, which measures the accuracy of the positive predictions. The precision score is compared against a benchmark to assess if the model performs better than a random guess.

## Usage

1. **Clone the repository**:
    ```sh
    git clone https://github.com/sumansatyal/bitcoin-price-prediction.git
    cd bitcoin-price-prediction
    ```

2. **Install dependencies**:
    ```sh
    pip install -r requirements.txt
    ```

3. **Run the script**:
    ```sh
    python bitcoin_price_prediction.py
    ```

## Results

- The initial Random Forest model achieved a precision score of approximately 69.23%.
- After implementing backtesting and adding additional predictors, the model achieved a precision score of approximately 47.52%.

## Conclusion

The project demonstrates the process of using machine learning for time series forecasting, specifically predicting Bitcoin price movements. While the initial model showed some predictive power, further enhancements and sophisticated techniques are needed for better accuracy and reliability.

## Limitations and Future Work

- **Overfitting**: The model may overfit to the training data, especially with complex models and many predictors.
- **Feature Engineering**: Additional domain-specific features could improve the model.
- **Advanced Models**: Exploring more advanced models like LSTM, GRU, or other neural networks tailored for time series data might yield better results.
- **Economic Indicators**: Incorporating external economic indicators and sentiment analysis from news and social media could enhance prediction accuracy.

## References

- [Yahoo Finance API](https://pypi.org/project/yfinance/)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html)
- [Pandas Documentation](https://pandas.pydata.org/docs/)

