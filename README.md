🚗 Used Car Price Prediction
This is a machine learning project that predicts the price of used cars based on their features.

It uses a dataset of used car listings from India and a Linear Regression model to estimate the car's value. The entire data cleaning and modeling process is bundled into a scikit-learn Pipeline, which automates preprocessing and prediction.

🎯 Project Goal
The main goal of this project is to build a reliable regression model that can predict the price of a used car given its:

Name

Company

Year of manufacture

Kilometers driven

Fuel type

🔧 Technologies Used
Python 3

Pandas: For data cleaning and manipulation.

Scikit-learn: For building the machine learning pipeline.

OneHotEncoder: To handle categorical features.

LinearRegression: The regression model.

make_column_transformer: To apply different transforms to different columns.

make_pipeline: To chain all the steps together.

r2_score: To evaluate model performance.

Jupyter Notebook: As the development environment.

📈 Project Workflow
Load Data: The raw CSV file is loaded into a pandas DataFrame.

Data Cleaning:

Price: Removed rows containing non-numeric values like "Ask for Price".

Year: Removed rows with non-numeric or invalid year values.

KMS Driven: Removed "kms" suffix and commas, then converted the column to an integer.

Name: Simplified the name column by keeping only the first 3 words (e.g., "Mahindra Quanto C8") to reduce high cardinality.

Typos: Corrected column name typos (e.g., yaer to year).

Missing Values: Handled NaN values.

Feature Engineering: The company column was extracted from the name column.

Modeling (Pipeline): A scikit-learn pipeline was built to automate the entire process:

Column Transformer: A make_column_transformer is used to:

Apply OneHotEncoder to the categorical columns (name, company, fuel_type).

Use remainder='passthrough' to let the numeric columns (year, kms_driven) pass through unchanged.

Model: The output of the transformer is fed directly into a LinearRegression model.

Error Handling: The OneHotEncoder uses handle_unknown='ignore' to prevent crashes if it sees a new car model during prediction.

Model Training: The pipeline was trained on 80% of the data.

Model Evaluation: The model's performance was evaluated on the 20% test set using the R-squared (R²) score.
