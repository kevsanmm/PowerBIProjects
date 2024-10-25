
# Bitcoin Price Analysis with Daily Change and Power BI Integration

## Project Overview

This project involves analyzing Bitcoin price data over a specified period using the CoinGecko API. The dataset has been enhanced with additional columns such as daily percentage change, 7-day moving averages, and price categories, which are then visualized in Power BI for deeper insights.

## Data Source

- **API**: The data is retrieved using the [CoinGecko API](https://www.coingecko.com/en/api) to get historical market data for Bitcoin.
- **Parameters**: 
  - Cryptocurrency: `Bitcoin`
  - Currency: `USD`
  - Time Period: `Last 120 days`

## Data Processing

The raw data consists of timestamps and prices, and the following transformations have been applied:

### Columns Added

1. **Daily Percentage Change (`daily_change`)**: 
   - This column calculates the percentage change between consecutive days to show the daily volatility of Bitcoin's price.
   - Formula:
     \[
     	ext{daily_change} = \left( rac{	ext{price_new} - 	ext{price_old}}{	ext{price_old}} ight) 	imes 100
     \]

2. **7-Day Moving Average (`moving_average_7`)**: 
   - The rolling average over the past 7 days is calculated to smooth short-term fluctuations and highlight longer-term trends.

3. **Maximum and Minimum Prices (`max_price_value` and `min_price_value`)**: 
   - These columns capture the highest and lowest prices within a 7-day window to identify key local price extremes.

4. **Price Category (`price_category`)**: 
   - Based on historical price percentiles, the prices are categorized into bins (e.g., `Very Low`, `Low`, `Medium`, `High`, `Very High`) to allow for easy interpretation and segmentation in visualizations.

### Additional Columns
- **Timestamp Breakdown**: The `timestamp` column is broken down into new columns like `year`, `month`, `day`, and `hour` to facilitate time-based analysis.
- **ID**: A sequential `id` column was added for indexing purposes.

## Data Visualization in Power BI

### Key Visualizations

1. **Bitcoin Price Time Series with Identified Valleys**:
   - A line chart showing Bitcoin's price over time, with red markers highlighting relative valleys (local minima) based on the calculated minimum values.

2. **Price Change Distribution**:
   - A histogram or bar chart displaying the distribution of daily percentage changes (`daily_change`), helping users understand volatility patterns.

3. **Price Category Insights**:
   - A categorical breakdown of prices based on predefined bins (`price_category`), useful for comparing periods of high vs. low prices.

### Customization in Power BI

- **Daily Change Formatting**: The `daily_change` values are formatted as percentages for clarity and ease of interpretation in Power BI.

## Next Steps

- **Backtesting**: We will continue by analyzing historical price data to see how well current price movements align with past trends.
- **Advanced Dashboards**: Plans are in place to create more advanced dashboards in Power BI, which will include forecasting, anomaly detection, and deeper exploration of correlations with market events.

## How to Run This Analysis

1. **Python Script**: The data processing script uses Python to fetch the data from the CoinGecko API, process it, and prepare it for visualization. The script can be executed in any Python environment, such as Jupyter Notebook.
   
2. **Power BI**: After the data is processed, import the resulting DataFrame into Power BI and use the predefined visualizations to explore the insights.

