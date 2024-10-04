# House Price Prediction using Machine Learning

This project predicts house prices based on various features such as location, area, number of bedrooms, bathrooms, etc. The model was trained using a dataset that contains real estate data and serves predictions via a Flask-based web app.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Dataset](#dataset)
- [Model Details](#model-details)
- [API Endpoints](#api-endpoints)
- [Results](#results)
- [Future Enhancements](#future-enhancements)
- [Contributors](#contributors)

## Project Overview
This machine learning project is designed to predict house prices using a regression model. The web application allows users to input house-related features (like square footage, number of rooms, etc.), and returns the predicted price of the house. 

The main aim of this project is to help users get an estimate of house prices based on various input factors, making it useful for home buyers, real estate agents, or investors.

## Technologies Used
- **Python**: The core programming language used.
- **Flask**: To serve the machine learning model via a web interface.
- **scikit-learn**: For implementing and training the machine learning model (Linear Regression).
- **pandas** and **numpy**: For data processing and manipulation.
- **HTML/CSS**: To build a simple front-end interface.
- **Git**: For version control.

## Setup Instructions

### 1. Clone the Repository
To get a copy of the project up and running locally, first, clone the repository:
```bash
git clone https://github.com/your-username/house-price-prediction.git
2. Create and Activate Virtual Environment
You should use a virtual environment to avoid dependency conflicts:

bash
Copy code
# For Windows
python -m venv venv
venv\Scripts\activate

# For Mac/Linux
python3 -m venv venv
source venv/bin/activate
3. Install Dependencies
Install the required Python libraries by running:

bash
Copy code
pip install -r requirements.txt
4. Run the Flask Server
Once dependencies are installed, you can run the Flask development server:

bash
Copy code
python server.py
The application will start on http://127.0.0.1:5000/. You can open this URL in your browser to interact with the web app.

Dataset
The dataset used for this project contains features such as the number of bedrooms, bathrooms, lot size, year built, and more. You can download the dataset from Kaggle House Prices Dataset, or use any similar dataset.

Features:
LotArea: Total area in square feet
YearBuilt: Year when the house was built
TotalRooms: Number of rooms
Neighborhood: Location of the house
SalePrice: The target variable, representing the sale price of the house.
Ensure that the dataset is in the data/ folder for the project to run successfully.

Model Details
We have used a Linear Regression model for this project. The features were preprocessed, cleaned, and used to train the model. After training, the model was serialized (pickled) for deployment via Flask.

Model Training
To retrain the model with new data:

Open the Jupyter notebook model_training.ipynb.
Run the cells to load, preprocess the data, and train the Linear Regression model.
Export the model using joblib.dump() or pickle for future use.
API Endpoints
The Flask app provides an API to interact with the model.

1. POST /predict
Description: Takes in house-related features and returns the predicted price.
Request Format: JSON
json
Copy code
{
  "area": 2400,
  "bedrooms": 3,
  "bathrooms": 2,
  "year_built": 2005,
  "neighborhood": "Downtown"
}
Response:
json
Copy code
{
  "predicted_price": 450000
}
Results
The model achieved an R² score of 0.85 on the test set, meaning that it can explain 85% of the variance in house prices.
Example of predictions:
Input: Area: 2400 sqft, Bedrooms: 3, Bathrooms: 2
Predicted Price: $450,000
Future Enhancements
