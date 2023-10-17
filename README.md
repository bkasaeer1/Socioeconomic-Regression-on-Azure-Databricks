# Project Title: Finding the Most Influencial Indicators of Broadband Adoption in United States Counties

## Project Description
This project aims to provide data-driven solutions to bridge the digital divide in the United States by harnessing the power of big data analytics within the Azure Databricks environment. It encompasses data preprocessing, exploratory data analysis, feature selection, and the development of predictive models to identify and comprehend the socio-economic factors influencing internet accessibility. Through a holistic approach that involves data analysis, visualization, and machine learning, the project seeks to provide valuable insights for informed policy decisions and initiatives aimed at reducing the digital divide.

**Key Steps:** Data Import, Exploratory Data Analysis, Model Selection, Hyperparameter Tuning, and Production Model Deployment.

## Azure Databricks Environment Setup

The code provided here sets up the Azure Databricks environment for big data analytics. It begins by importing a range of essential Python libraries commonly used for data analysis, visualization, and machine learning, such as PySpark, Seaborn, Matplotlib, XGBoost, Pandas, and NumPy. These libraries facilitate data preprocessing, regression analysis, feature selection, and hyperparameter tuning within the Azure Databricks platform, making it an ideal environment for comprehensive big data analytics. Various settings are configured to enhance data visualization, interactivity, and user experience.

## Step 1: Data Import & Preprocessing

This code snippet specifies the location and type of a data file containing the 2019 American Community Survey 5-year estimates for socio-economic and broadband-related parameters. It loads the data into a DataFrame, applies data transformations, selects relevant columns, and formats the FIPS code. It also identifies target and feature columns, providing a preliminary examination of data distributions.

## Step 2: Review Data Schema and Records

In this step, the code displays the first two rows of the DataFrame to validate record values and data types. It also prints the schema of the DataFrame to understand its structure.

## Step 3: Generating a Comprehensive Summary Table from Spark Dataframe

This code generates a summary table for the DataFrame by calculating quantiles, such as percentiles and statistics like mean, count, minimum, and maximum. It also provides information about missing values for each column in the DataFrame, presenting a comprehensive overview of the data.

## Step 4: Interactive Feature Distribution Visualization

This section focuses on creating dynamic plots using Databricks selector widgets. Users can select two different variables for comparison and observe their distributions interactively. The code generates dynamic selector widgets, retrieves selected attributes, and creates histograms to visualize feature distributions.

## Step 5: Dendrogram-Based Correlation Analysis

In this step, dendrograms are generated to evaluate correlations among variables using both Pearson and Kendall correlation coefficients. The code sets plot variables, creates dynamic selectors for correlation methods, and plots correlation dendrograms to visualize relationships between variables.

## Step 6: Stratified Sampling for Addressing Internet Accessibility Disparities

The primary goal of this predictive model is to address the digital divide in the United States. To mitigate bias during model training, a stratified sampling approach is employed. This ensures that disadvantaged counties are proportionally represented in training, testing, and validation datasets, preventing overfitting to the majority class.

## Step 7: Data Preparation for PySpark Machine Learning

This code prepares datasets for machine learning training, handling labels, selecting features, and dealing with missing values. It creates datasets for training, validation, and testing, organized into a dictionary for easy access.

## Step 8: Visualize Inspection of Histograms

This section visualizes histograms of target and predictor variables for outlier detection and normality assessment.

## Step 9: Impact of Data Transformation on Regression Model Performance

The code evaluates the impact of data transformation on regression model performance, focusing on an Elastic Net regressor as a baseline. It compares different data and model enhancements and reports their effectiveness.

## Step 10: Impact of Standardization on XGBoost Regressor Performance

This step assesses the impact of standardization on the performance of an XGBoost Regressor, emphasizing the benefits of standardization for this model.

## Step 11: Analyzing the Relationship Between Selected Variables and Internet Access

One-dimensional Partial Dependence Plots (PDP) and Individual Conditional Expectation (ICE) plots are used to explore the relationships between socio-economic explanatory variables and internet access. These plots provide insights into variable interactions and their impact on the target variable.

## Step 12: Exploring Interactions Between Pairs of Predictor Variables

Two-dimensional Partial Dependence Plots (PDP) are examined to visualize the joint influence of features on the target variable. The results highlight the relationship between pairs of predictor variables and their combined impact on internet access.

## Step 13: Feature Selection

A comprehensive exploration of feature selection methods is undertaken to identify the top 5 most significant features. Various techniques are applied, and a majority voting approach is employed to ensure robustness in the final feature selection.

## Step 14: Data Transformation

A transformer pipeline is created based on the feature selection strategy and scaling method determined in the Exploratory Data Analysis (EDA) phase. The pipeline prepares data for subsequent modeling steps.

## Step 15: Model Selection Using AutoML in Databricks

Automated methods for model selection, such as AutoML, are employed. AutoML explores various models, including Linear Regression, Decision Tree, Random Forest, LightGBM, and XGBoost, using the training dataset. Model performance is assessed, and the XGBoost Regressor is identified as the best model.

## Step 16: Fine Tuning the XGBoost Regressor

Hyperparameter tuning for the XGBoost Regressor is conducted using Hyperopt. Optimal hyperparameters are determined, and model performance metrics are logged using MLflow.

## Step 17: Hyperparameter Tuning and Training of XGBoost Regressor for Persistence in Production

The hyperparameter tuning process using Hyperopt was carried out for the XGBoost Regressor, resulting in optimal hyperparameters. Subsequently, a persistence model was trained with these optimal settings for later use in production. The configuration parameters were captured and logged with MLflow. The model was trained on the combined training and validation sets, and its predictions on the test set were recorded.

## Step 18: Registering the Final Model for Production Deployment

The final model is registered with the MLflow model registry. The registration process is monitored until the newly registered model transitions from the 'PENDING_REGISTRATION' status to 'READY.' Once the model reaches the 'READY' status, it is moved to the 'production' stage in the model registry.
