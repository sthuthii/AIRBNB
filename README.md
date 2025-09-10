📘 Airbnb Price Prediction – Regression Project

📌 Overview


The workflow:

Data exploration & visualization

Train/test split with stratified sampling

Feature preprocessing (numerical & categorical)

Building regression models (Linear Regression, Decision Tree, Random Forest)

Model evaluation using RMSE



---

📂 Dataset

We use the Seattle Airbnb Open Data from Kaggle.

After downloading and extracting, the dataset contains multiple files:

listings.csv → detailed listing information (we use this)

calendar.csv → availability & price calendar

reviews.csv → guest reviews


For this project, we only use listings.csv.


---

📑 Selected Features

We reduce the dataset to a clean subset of columns:

Column Name	Description	Type	Notes

accommodates	How many guests the listing can host	Numerical	
bedrooms	Number of bedrooms	Numerical	May contain NaN
bathrooms_text	Number/type of bathrooms	Text → Num	Needs parsing (e.g., “1.5 baths”)
number_of_reviews	Total number of reviews	Numerical	
review_scores_rating	Average rating (0–100 scale)	Numerical	Missing values → imputed
latitude	Latitude coordinate	Numerical	
longitude	Longitude coordinate	Numerical	
neighbourhood	Neighborhood name	Categorical	One-hot encoded
price	Nightly price (target variable)	Numerical	Cleaned from $1,200.00 → 1200.0



---

⚙ Preprocessing Steps

1. Load dataset (listings.csv or listings.xlsx)


2. Select relevant columns (above list)


3. Clean data:

Convert price to float

Parse bathrooms_text → numeric value

Handle missing values (fillna or drop)



4. Stratified Sampling:

Create price bins to ensure balanced train/test splits



5. Feature Engineering:

Standardize numerical features

One-hot encode neighbourhood



6. Save processed dataset as airbnb_clean.csv




---

📊 Data Visualization


Price distribution histogram

Correlation heatmap

Scatter plots:

latitude vs longitude colored by price (to visualize location-price trends)

accommodates vs price

number_of_reviews vs price




---

🤖 Models Trained

Linear Regression

Decision Tree Regressor

Random Forest Regressor


Evaluation metric: Root Mean Squared Error (RMSE)


---

🚀 How to Run

1. Install Dependencies

pip install pandas numpy matplotlib seaborn scikit-learn

2. Preprocess the Dataset

python preprocess_airbnb.py

This script will generate a cleaned dataset airbnb_clean.csv.

3. Run the Regression Pipeline

python airbnb_regression.py


---

📈 Results (Example)

Linear Regression RMSE: ~200

Decision Tree RMSE: ~150

Random Forest RMSE: ~120


(Values vary depending on preprocessing choices)
