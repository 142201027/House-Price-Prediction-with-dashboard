This repository contains a complete, end-to-end data science project that predicts house prices in Indian metropolitan areas. The project encompasses the entire machine learning workflow, from data cleaning and feature engineering to model training, optimization, and finally, visualization in an interactive Power BI dashboard.

## Project Overview

The real estate market is complex, with prices influenced by numerous factors. This project aims to demystify these dynamics by building a robust regression model to predict property prices accurately. The final output is not just a model, but a user-friendly and interactive Power BI dashboard that allows users to explore data, view predictions, and understand the key drivers of the housing market. [1, 2, 3]

This project serves as a practical demonstration of a full data science pipeline, integrating Python's analytical power with Power BI's visualization capabilities.

## Key Features

  - Data Cleaning & Preprocessing: Implements a pipeline to handle messy, real-world real estate data, including missing values, inconsistent formatting, and outliers.
  - Exploratory Data Analysis (EDA): Uncovers trends, patterns, and correlations in the housing market through comprehensive data visualization.
  - Feature Engineering: Creates new, impactful features from existing data (e.g., `price_per_sqft`) to improve model accuracy.
  - Predictive Modeling: Trains and evaluates both a baseline Linear Regression model and a regularized Ridge Regression model for price prediction.
  - Model Optimization: Utilizes K-Fold Cross-Validation and `GridSearchCV` to systematically tune hyperparameters and select the most robust model.
  - Power BI Integration: Leverages Python scripting within Power BI's Power Query Editor to apply the trained machine learning model directly to the data, generating a `Predicted_Price` column.
  - Interactive Dashboard: Presents the data and model predictions in a dynamic and visually appealing Power BI dashboard, complete with slicers, drill-throughs, and performance analysis visuals.

## Tech Stack

  - **Programming Language: Python 3
  - **Libraries:
      - **Data Manipulation & Analysis:** Pandas, NumPy [2]
      - **Machine Learning:** Scikit-learn [2]
      - **Data Visualization (Python):** Matplotlib, Seaborn [2]
  - **Business Intelligence:** Microsoft Power BI [18]

## Project Workflow

The project follows a structured, multi-stage workflow:

1.  **Data Sourcing and Cleaning:** The dataset (e.g., Bangalore House Price Data from Kaggle) is loaded. A rigorous cleaning process is applied to handle missing values, correct data types, and standardize unstructured text fields (like `total_sqft` and `size`). [4, 6]
2.  **Exploratory Data Analysis (EDA):** Visualizations such as histograms, scatter plots, and correlation heatmaps are used to understand feature distributions and their relationships with the target variable (`price`). [7, 9]
3.  **Feature Engineering:** New, more predictive features like `price_per_sqft` are created. Categorical variables are converted into a machine-readable format using one-hot encoding. [10, 12]
4.  **Model Training and Optimization:** The data is split into training and testing sets. Features are scaled using `StandardScaler`. A baseline Linear Regression model is built, followed by a Ridge Regression model. `GridSearchCV` is used to find the optimal `alpha` hyperparameter for the Ridge model, ensuring it is robust and generalizes well. [13, 14, 22]
5.  **Model & Data Export:** The final trained Ridge model and the feature scaler are saved as `.pkl` files. The test dataset is saved as a `.csv` file for use in Power BI.
6.  **Power BI Integration & Visualization:** The test data CSV is loaded into Power BI. A Python script is executed within the Power Query Editor to load the saved model and scaler, make predictions, and append them as a new column. Finally, an interactive dashboard is designed to visualize the results and allow for dynamic data exploration. [19]

## Setup and Installation

Follow these steps to set up and run the project on your local machine.

### Prerequisites

  - Python (3.7 or newer)
  - Microsoft Power BI Desktop

### 1\. Clone the Repositorybash

git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
cd your-repository-name

````

### 2. Set Up the Python Environment
It is highly recommended to use a virtual environment.
```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows
venv\Scripts\activate
# On macOS/Linux
source venv/bin/activate
````

### 3\. Install Dependencies

Install all the required Python libraries from the `requirements.txt` file.

```bash
pip install -r requirements.txt
```

*(**Note:** If a `requirements.txt` file is not in the repository, you can create one from your project environment using `pip freeze > requirements.txt`)*

### 4\. Run the Jupyter Notebook

Open and run the Jupyter Notebook (`.ipynb` file) included in this repository. This will perform the data cleaning, model training, and will generate three essential files:

  - `ridge_model.pkl` (the trained model)
  - `scaler.pkl` (the feature scaler)
  - `test_data_for_power_bi.csv` (the data for visualization)

### 5\. Configure Power BI

1.  **Open the `.pbix` file** in Power BI Desktop.
2.  **Configure Python Path:** Go to `File > Options and settings > Options > Python scripting`. Ensure that the detected Python home directory points to the virtual environment you created. [19]
3.  **Update File Paths in Power Query:**
      - Click on **Transform data** to open the Power Query Editor.
      - In the **APPLIED STEPS** pane, click the gear icon next to the **"Ran Python script"** step.
      - In the Python script editor window, **update the file paths** for `ridge_model.pkl` and `scaler.pkl` to match their location on your local machine.
      - Click **OK, then Close & Apply.
Usage

Once the setup is complete, you can interact with the Power BI dashboard:

  - Use the slicers on the side to filter the data by `location`, `BHK`, and other features.
  - Analyze the **Actual vs. Predicted Price** scatter plot to assess model accuracy.
  - Explore the map to see geographical price distributions.
  - Right-click on visuals and use the **Drill-through** feature to navigate to detailed views.

## Contributing

Contributions are welcome\! If you have suggestions for improvements, please follow these steps:

1.  Fork the Project.
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the Branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.
