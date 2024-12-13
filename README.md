# StockSense-A-Financial-Decision-Making-Tool-for-Stock-Market-Investments
A user-friendly financial tool leveraging big data and modern architectures to provide stock rankings and investment insights tailored to individual timelines and risk profiles.

# StockSense: A Financial Decision-Making Tool for Stock Market Investments

StockSense is an innovative financial tool designed to simplify stock market investments by providing actionable insights and tailored stock rankings. Built with a robust data pipeline and user-focused design, it empowers individuals with or without financial expertise to make informed decisions.

## Project Overview

Navigating the complexities of the stock market can be challenging, especially for beginner investors. StockSense offers a seamless solution, leveraging real-time data and advanced analytics to rank stocks based on volatility, growth, and other key metrics. The system is designed to adapt to users' financial timelines, whether short-term or long-term.

### Key Features:
- **Automated Data Processing Pipeline:** Utilizes modern architectures like Kafka, Hadoop, and Spark for efficient data handling.
- **Custom Ranking System:** Combines metrics such as volatility, growth, and volume change to rank stocks effectively.
- **Risk Management Integration:** Applies strategies to temper market volatility and optimize returns.
- **User-Friendly Interface:** Requires minimal financial expertise to operate, making it accessible to all users.

## Methodology

1. **Data Collection:**
   - Fetches real-time stock data from Yahoo Finance based on user-specified tickers and timeframes.
   - Stores data in HDFS and publishes it to a Kafka topic for further processing.

2. **Data Processing:**
   - Handles missing values and extracts meaningful features such as rolling window statistics and lagged features.
   - Computes financial metrics to aid ranking.

3. **Stock Ranking System:**
   - Sub-ranks are computed for volatility, growth, volume change, and rolling average close change.
   - Final rank is derived using weighted sub-rank aggregation.

4. **Risk Management:**
   - Incorporates strategies to reduce risk and align portfolio with user goals.
   - Regular rebalancing and performance monitoring to maintain alignment with financial objectives.

## StockSense Pipeline

The system pipeline includes the following components:
1. Fetch stock data from Yahoo Finance.
2. Combine data into a `.json` file and publish to Kafka.
3. Save data to HDFS for storage and processing.
4. Process data with Apache Spark to compute rankings and metrics.
5. Provide user-input-driven analysis for tailored recommendations.


## Ranking System

The ranking system uses the following formula:
\[ R_f = w_v \times R_v + w_g \times R_g + w_{vc} \times R_{vc} + w_{rac} \times R_{rac} \]
Where:
- \( R_v, R_g, R_{vc}, R_{rac} \) are sub-ranks for volatility, growth, volume change, and rolling average close change.
- \( w_v, w_g, w_{vc}, w_{rac} \) are respective weights assigned to each sub-rank.

## Why Use StockSense?

- **In-Depth Market Analysis:** Leverages trends and company data for informed stock selection.
- **Risk Management Expertise:** Reduces market volatility impacts while enhancing returns.
- **Performance Monitoring:** Offers continuous portfolio evaluation and rebalancing.
- **Customization:** Adapts strategies to align with individual financial goals and timelines.
