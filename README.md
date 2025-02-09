# Stock Price Prediction using Support Vector Machine (SVM)

## Overview

This project demonstrates stock price prediction using the **Support Vector Machine (SVM)** algorithm. The focus is on five key stocks: Reliance, M&M, Lemon Tree, PNB, and HDFC Bank. The model is trained using historical stock data, and predictions are made based on features like `Open`, `High`, `Low`, and `Close` prices.

## Project Workflow

1. **Data Collection**:
   - Stock data for **Reliance**, **M&M**, **Lemon Tree**, **PNB**, and **HDFC Bank** was collected using the [Yahoo Finance API](https://pypi.org/project/yfinance/).
   - The historical data for the period of June 2022 to June 2024 was downloaded.

2. **Data Cleaning**:
   - Unnecessary columns like `Adj Close` and `Volume` were dropped from the dataset.

3. **Visualization**:
   - **Time Series Plot**: Closing prices were plotted to visualize trends over time.
   - **Moving Averages**: The 20-day and 200-day moving averages were computed and plotted for trend analysis.
   - **Volatility**: The daily price range (difference between `High` and `Low`) was plotted to observe volatility.

4. **Modeling**:
   - Input features used for training the model: `Open`, `High`, `Low`, `Close` prices.
   - Target variable: Binary output indicating whether the stock price increased (1) or decreased (0) the next day.
   
5. **Train-Test Split**:
   - Data was split into an 80% training set and a 20% test set.
   
6. **Preprocessing**:
   - **Standardization**: Data was standardized using `StandardScaler` for better performance of the SVM model.

7. **Hyperparameter Tuning**:
   - Grid search with cross-validation (`GridSearchCV`) was used to find the best parameters for the SVM model.

8. **Model Training**:
   - An **SVM** classifier was trained on the training data using the best parameters found during tuning.

9. **Model Evaluation**:
   - Model performance was evaluated using accuracy score and confusion matrix.
   
10. **Daily P&L Calculation**:
    - Profit and Loss (P&L) was calculated based on predicted `Buy` and `Sell` signals, and gross profit was computed.

11. **Sharpe Ratio Calculation**:
    - The **Sharpe Ratio** was calculated to assess the risk-adjusted returns.

## Key Metrics

- **Gross Profit**: Computed based on daily P&L.
- **Exposure**: The final stock price multiplied by the lot size.
- **Sharpe Ratio**: Measure of risk-adjusted return, calculated using daily P&L.
- **Drawdown**: Maximum drop in cumulative profit.

## Stock-Specific Analysis

Each stock’s data is saved in separate CSV files that include important metrics like drawdown profit and P&L for further analysis.

### Example Stock: Reliance

- **Confusion Matrix**: Confusion matrix showing the model's performance.
- **Accuracy**: Accuracy of the model on the test set.
- **Gross Profit**: Calculated from daily P&L.
- **Sharpe Ratio**: Indicates risk-adjusted performance.
- **Drawdown**: Maximum drawdown during the trading period.

## Requirements

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Yahoo Finance API (`yfinance`)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/stock-prediction-svm.git
    ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the script:
    ```bash
    python stock_prediction.py
    ```

## Files

- **`stock_prediction.py`**: Main Python script containing the logic for data fetching, preprocessing, model training, and evaluation.
- **`Internal_calc/*.csv`**: CSV files containing the analysis results for each stock.

## Results

The model was evaluated based on accuracy, confusion matrix, and other trading metrics like Sharpe ratio and drawdown. These metrics help in understanding the model’s performance from both a technical and financial perspective.

## Future Improvements

- Addition of more advanced trading strategies like trailing stop-loss and moving stop-loss.
- Use of different machine learning models (e.g., Random Forest, XGBoost) to compare performance.
- Implementation of reinforcement learning-based trading strategies.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
