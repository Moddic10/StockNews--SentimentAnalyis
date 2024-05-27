### 📈 Stock Price Prediction with News Sentiment Analysis 📰

This data pipeline project moves data from API's to an SQL database and combines several elements: Public API access, data pipelines with MySQL, and Python for data manipulation, machine learning, and visualization.

#### Data Sources:
- 📊 **Stock Data API:** Utilized [Rapid API/Nairobi Stock Exchange](https://rapidapi.com/iancenry/api/nairobi-stock-exchange-nse/) to retrieve historical and real-time stock price data.
- 📰 **News API:** Integrated [World News API](https://www.worldnewsapi.com/) to gather news articles related to Safaricom company which I chose. You need to obtain an API key to make requests to the API and add request params such as source-countries = 'ke' and text = 'safaricom' to get specific news.

#### SQL Schema and Tables:
- 🗃️ **Stocks Data Table:** Stores historical stock data including ticker, name, volume, price, change, and date.
- 🗞️ **News Data Table:** Stores news articles including article ID, title, text, URL, publish date, author, language, source country, and sentiment.

#### Project Workflow:
1. ⚙️ **Data Extraction:** Extracted historical and real-time stock price data using Alpha Vantage API.
2. 🚀 **Data Loading:** Loaded the extracted data into the MySQL database.
3. 🛠️ **Data Preprocessing:** Preprocessed the stock data for machine learning, handling missing values, and creating new features.
4. 📝 **Sentiment Analysis:** Performed sentiment analysis on news articles using NLTK and TextBlob, storing sentiment scores in the News Data Table.
5. 🔄 **Data Merging:** Merged stock data with average daily sentiment scores.
6. 🤖 **Machine Learning Model:** Trained a machine learning model using Scikit-learn to predict future stock prices based on historical data and sentiment features.
7. 📊 **Model Evaluation:** Evaluated the model using Mean Squared Error (MSE) and R-squared metrics.
8. 📈 **Visualization:** Visualized the predicted prices against the actual closing prices.

#### Files Description:
- ⚙️ **db_config.py:** Contains the database configuration settings.
- 🔄 **db_operations.py:** Handles database operations such as connecting to the database, executing queries, and fetching results.
- 🚀 **load_model.py:** Loads the machine learning model, performs data preprocessing, and evaluates the model's performance.
- 📰 **load_news_pipeline.py:** Implements the pipeline for fetching and processing news data, including sentiment analysis.
- 📊 **load_stocks_pipeline.py:** Implements the pipeline for fetching and processing stock data from the API.
- 🔧 **transform_pipeline.py:** Contains functions for processing, transforming and cleaning data for machine learning models.

#### Environment Variables (`.env` file):
- Contains sensitive information such as API keys and database credentials. Not included in the repository.

#### Model Score and Accuracy:
- **Training and Testing Sets Shapes:** (8, 2) (3, 2) (8,) (3,)
- **MSE:** 0.00033765568078515055
- **R2:** 0.8822131346098291

#### To Run the Project:
1. Clone the repository.
2. Create a `.env` file with API keys and database credentials.
3. Install dependencies (`pip install -r requirements.txt`).
4. Run `python index.py` to execute the project.

### Stock Prediction Graph:
![Visualization](<graph.png>) 

### Conclusion:
This project showcases the integration of multiple APIs, data analysis, sentiment analysis, feature engineering, and machine learning for stock price prediction.
