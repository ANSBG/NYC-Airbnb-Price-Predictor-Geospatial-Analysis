
🗽 NYC Airbnb Price Predictor & Geospatial Analysis
An Advanced Machine Learning Project for Real Estate Estimation

📖 Project Overview :

Pricing a rental property correctly is a complex challenge involving location, amenities, and market demand. This project analyzes over 48,000 New York City Airbnb listings to determine the key drivers of price.
It moves beyond simple analysis by engineering advanced geospatial and text-based features to train a high-performance XGBoost model. The result is a tool capable of predicting the nightly rate of a listing with high accuracy.

🏆 Key Results :

By implementing advanced feature engineering (Distance to City Center, NLP on listing names) and using XGBoost with Log-Transformation, this project achieved:
Mean Absolute Error (MAE): $36.30
Interpretation: On average, the model's price prediction is within ~$36 of the actual listing price.
Performance Upgrade: The use of XGBoost and "Distance to Times Square" features improved accuracy significantly over a standard Random Forest baseline.

🛠️ Tech Stack & Methods :
Language: Python 3.10+
Data Processing: Pandas, NumPy (Log-transforms for skew handling)
Geospatial: Folium (Interactive Heatmaps), Haversine Formula (Distance calculation)
Machine Learning: XGBoost (Extreme Gradient Boosting), Scikit-Learn
Natural Language Processing (NLP): Keyword extraction from listing descriptions (e.g., "Luxury", "View").

⚙️ Methodology (How I lowered the Error) :

To minimize the error (MAE) down to $36.30, several advanced techniques were applied:
Target Log-Transformation:
Airbnb prices are highly right-skewed (many cheap rooms, few expensive penthouses).
I applied np.log1p() to the target variable to normalize the distribution, allowing the model to learn stable patterns.
Geospatial Feature Engineering:
Raw Latitude/Longitude coordinates are hard for tree models to interpret effectively.
I calculated the Haversine Distance from every listing to Times Square (NYC Center), giving the model a concrete "Location Value" metric.

NLP / Text Mining:

Extracted high-value keywords (e.g., "Penthouse", "Private", "Garden") from the name column to capture premium attributes not listed in the standard features.
Model Selection:
Switched from Random Forest to XGBoost, which handles outliers and missing values more effectively.

📊 Visualizations :

<img width="1053" height="603" alt="image" src="https://github.com/user-attachments/assets/eb2616e7-35a3-438c-9bc2-add26b00513b" />

🔮 Future Improvements :

Sentiment Analysis: Analyze the reviews text to see if positive sentiment scores correlate with price hikes.
External Data: API integration with WalkScore or Crime Data to add neighborhood safety features.
Deployment: Build a Flask API endpoint to serve predictions in real-time.

Author : ANASS BOUGADOUM
