Leveraging Convolutional Neural Networks (CNNs) to Forecast 10-Day Returns from Stock Chart Images

By Jesse Leone

Project Overview
Stock charts have long been used to guide trading and investment decisions, with early traders even hand-drawing charts to spot patterns and trends. This project builds on that tradition by employing modern image recognition techniques—specifically Convolutional Neural Networks (CNNs)—to analyze candlestick chart images, aiming to generate valuable insights for stock forecasting.

Methodology
This project utilized daily stock price data from the 30 companies listed in the Dow Jones Industrial Average (DJIA), retrieved from the Yahoo Finance API. Each data sample was transformed into stock chart images, with every chart representing the preceding 100 trading days. The objective was to predict the stock's price 10 days into the future.

The charts were formatted as 107x107 pixel images, intentionally keeping the resolution low to simulate the challenge of capturing useful patterns. A blue line on each chart marks the 20-day moving average. The dataset was divided into training, validation, and test sets to ensure that predictions were always based on historical data, simulating real-world forecasting conditions.

Binary Classification Results
The first model used a binary CNN to determine whether a stock's price would rise or fall. The model’s performance was evaluated against the Dow Jones Industrial Average during the same out-of-sample period. Remarkably, the portfolio constructed using the model's predictions achieved a 56% return, significantly outperforming the DJIA’s 31% return.

What makes this even more notable is that the model performed well in both bullish and bearish markets, indicating that it successfully identified meaningful predictive features from the charts.

Multi-Class Classification Results
A second model applied multi-class CNNs to predict not only the direction of price movement but also the magnitude. The goal was to reduce the standard deviation of prediction errors compared to the typical standard deviation of stock returns.

While this may sound abstract, it offers tremendous value to options traders who rely on precise predictions about future price ranges to structure complex, high-reward trades. The negative Bartlett coefficient from this model confirms that the standard deviation of prediction errors was lower than that of market returns, and the p-value demonstrated statistical significance—highlighting the model’s practical utility.

Key Takeaways
Binary Classification Model: https://github.com/jesseleone/convolutional-neural-network-stock-charts/blob/main/Binary%20Results.JPG

Successfully outperformed the Dow Jones Industrial Average (56% vs. 31%).
Demonstrated consistent success across both rising and falling markets, suggesting it captures actionable patterns.
Multi-Class Model:

Achieved a lower standard deviation of prediction errors compared to stock returns, which is highly valuable for options traders.
Enables traders to take low-risk positions with high potential payoffs if the stock price lands within a specified range.

Future Research Directions
While these models delivered promising results, it is essential to emphasize that they are experimental and should not yet be used for real-world trading without further validation.

Potential areas for further exploration: https://github.com/jesseleone/convolutional-neural-network-stock-charts/blob/main/Diagram.JPG

Neural Network Optimization: Adjusting the architecture to improve the model’s ability to interpret stock chart patterns (consider K-fold and gridsearch)
Chart Parameters: Testing different values for the number of days included, pixel resolution, and other indicators (e.g., trading volume).
Expanded Stock Universe: Incorporating stocks no longer listed in the DJIA or those that have gone private to mitigate survivorship bias.
Expanded Timeframe: Increase lookback period or increasing period intervals (down to 1-minute).
Hybrid Neural Networks: Developing a model that combines numerical and visual data to enhance predictive performance.

Acknowledgements: 
- Jeongseok Bangl, Doojin Ryu. CNN-BASED STOCK PRICE FORECASTING BY STOCK CHART IMAGES.
- Kyle Johnson. Forecasting Stock Movements with Image Classification.
