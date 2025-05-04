Credit Score Prediction Model
Overview
This project aims to build a predictive model to estimate a person's annual income based on various features such as employment details, education, family structure, and more. Using PySpark for data preprocessing, feature engineering, and model building, the project explores both Linear Regression and Random Forest Regressor for predicting the Annual_income.

The dataset, Credit_card.csv, contains various attributes related to individuals' financial and demographic information, which is used to build the predictive model.

Table of Contents
Technologies

Installation

Dataset Description

Steps to Run the Code

Data Preprocessing and Feature Engineering

Model Building and Evaluation

Results

Licenses and Credits

Technologies
Python: Programming language used to write the code.

PySpark: Framework for big data processing.

JDK 8: Java Development Kit required for PySpark.

Matplotlib: Library for plotting results.

Pandas: For working with data in DataFrame format.

Installation
Follow these steps to get the environment up and running:

Install Java 8: Required for Spark.

Install JDK 8

Install Spark:

Download and install Spark by following these instructions.

Install Python dependencies:

bash
Copy
Edit
pip install pyspark matplotlib pandas
Download the dataset:

Ensure you have the Credit_card.csv dataset in the same directory as the script or update the file path in the code accordingly.

Dataset Description
The dataset Credit_card.csv contains various attributes related to individuals, including:

Type_Occupation: Occupation type (e.g., business, student, retired).

GENDER: Gender of the individual.

Car_Owner: Whether the individual owns a car (Y/N).

Propert_Owner: Whether the individual owns property (Y/N).

Housing_type: Type of housing (e.g., apartment, house).

Annual_income: Annual income of the individual (target variable).

Family_Members: Number of family members supported by the individual.

Employed_days: The number of days the individual has been employed.

Education: Education level (e.g., higher education, academic degree).

Marital_status: Marital status (e.g., married, single).

Steps to Run the Code
Setup Environment: Make sure you've installed Java 8, Spark, and Python libraries as described above.

Run the Script:

Open your terminal or command prompt.

Navigate to the directory containing the Python script and dataset.

Execute the script using Python:

bash
Copy
Edit
python credit_score_prediction.py
Data Preprocessing and Feature Engineering
The data preprocessing steps include:

Handling Missing Data: Missing values in Type_Occupation are filled with 'NA', and other rows are dropped if any nulls are present in critical columns.

Feature Transformation:

Negative Values: Absolute values are used for Birthday_count and Employed_days to ensure positive values for age and employment.

Age Calculation: The age is calculated using the Birthday_count field and today's date.

Income per Family Member: For those with family members, the Annual_income is divided by the Family_Members column.

Categorical Features Encoding:

Categorical columns like GENDER, Car_Owner, Propert_Owner, and others are encoded using StringIndexer and OneHotEncoder.

Feature Selection: The final model includes features like Income_per_Family_Member, Age, FR_score, and others.

Model Building and Evaluation
Two machine learning models are implemented and evaluated:

Simple Linear Regression (SLR):

The LinearRegression model is trained on the processed features.

Evaluation metric: Root Mean Squared Error (RMSE).

Random Forest Regressor (RF):

The RandomForestRegressor model is trained with 100 trees and a depth of 5.

Evaluation metric: RMSE.

Both models are evaluated on the test set, and the predicted annual income is compared with the actual values.

Results
After training both models, the following results were obtained:

Linear Regression RMSE:

plaintext
Copy
Edit
Root Mean Squared Error (RMSE) on test data for Simple Linear Regression = 55527.11877933004
Random Forest RMSE:
The evaluation results of the Random Forest model were visually plotted, showing the correlation between actual and predicted annual income.


Licenses and Credits
PySpark: The project uses the PySpark framework for data processing and machine learning.

Matplotlib: Used for plotting the predictions vs actual values.

Pandas: Used for data manipulation and conversion to DataFrame for ease of handling.
