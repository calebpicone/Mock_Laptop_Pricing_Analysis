# Laptop_Pricing_Analysis
Labs using mock laptop data to perform data analysis using Python. Jupyter Notebooks are part of IBM's "Data Analysis with Python" course.

----------------------------------------------------------------------------------------------------------------------------------------------------
## Overview - Laptop Pricing Data Set
The following is an overview of the provided data set used for the labs:

### Parameters
The parameters used in the dataset are:

#### Manufacturer
The company that manufactured the laptop

#### Category
The category to which the laptop belongs: This parameter is mapped to numerical values in the following way:

|  Category    |  Assigned Value  |
|--------------|------------------|
|  Gaming	     |  1               |
|  Netbook     |  2               |
|  Notebook	   |  3               |
|  Ultrabook   |  4               |
|  Workstation |  5               |

#### GPU
The manufacturer of the GPU. This parameter is mapped to numerical values in the following way:

|  GPU         |  Assigned Value  |
|--------------|------------------|
|  AMD	       |  1               |
|  Intel       |  2               |
|  NVidia	     |  3               |

#### OS
The operating system type (Windows or Linux): This parameter is mapped to numerical values in the following way:

|  OS          |  Assigned Value  |
|--------------|------------------|
|  Windows	   |  1               |
|  Linux       |  2               |

#### CPU_core
The type of processor used in the laptop: This parameter is mapped to numerical values in the following way:

|  CPU_core          |  Assigned Value  |
|--------------------|------------------|
|  Intel Pentium i3	 |  3               |
|  Intel Pentium i5  |  5               |
|  Intel Pentium i7	 |  7               |

#### Screen_Size_cm
The size of the laptop screen is recorded in cm.

#### CPU_frequency
The frequency at which the CPU operates, in GHz.

#### RAM_GB
The size of the RAM of the system in GB.

#### Storage_GB_SSD
The size of the SSD storage in GB is installed in the laptop.

#### Weight_kg
The weight of the laptop is in kgs.

#### Price
The price of the laptop is in USD.

----------------------------------------------------------------------------------------------------------------------------------------------------
## Notebook 1 - Importing Data Sets

### Key Skills Covered:
- Importing datasets into Pandas DataFrame
- Data cleaning (replacing missing or incorrect values)
- Adding headers to datasets
- Exploring basic data insights through summary statistics
- Understanding data types and their impact on analysis

### Libraries Used:
- pandas
- numpy

### Key Tasks & Insights:

#### 1. Importing the Dataset
- Loaded a dataset from a CSV file into a Pandas DataFrame (df).
- Confirmed successful loading by printing the first 5 rows of the dataset.

##### Findings:
- The dataset consists of laptop pricing data, including columns like Manufacturer, Category, Screen type, GPU, OS, CPU core count, screen size, CPU frequency, RAM size, storage, weight, and price.

#### 2. Adding Headers
- Added appropriate headers to the DataFrame to represent the columns more clearly.
- The headers include: "Manufacturer", "Category", "Screen", "GPU", "OS", "CPU_core", "Screen_Size_inch", "CPU_frequency", "RAM_GB", "Storage_GB_SSD", "Weight_kg", "Price".

##### Findings:
- The DataFrame was updated to reflect the new headers, improving its readability and structure.

#### 3. Data Cleaning (Replacing '?' with NaN)
- Replaced '?' values in the dataset with NaN using NumPy for further cleaning.

##### Findings:
- Missing or incorrect data represented by '?' was cleaned to avoid analysis errors and prepare the dataset for further analysis.

#### 4. Exploring Data Types
- Used df.dtypes to explore the data types of each column.

##### Findings:
- Columns like "Manufacturer", "Screen", "Weight_kg" are of object type, indicating categorical or textual data.
- Numerical columns such as "Category", "GPU", "CPU_core", "RAM_GB", "Storage_GB_SSD", "Price" are of integer or float type, which is suitable for numerical operations.

#### 5. Descriptive Statistical Analysis
- Generated a statistical summary of the dataset using df.describe(include='all').

##### Findings:
- The summary provided insights on the distribution of numerical variables like "Category", "GPU", "CPU_core", and "Price".
- The dataset contains a variety of manufacturers (with "Dell" being the most frequent), screen types, and price ranges. There are also some missing values in "Screen_Size_inch" and "Weight_kg" columns.

#### 6. Summary Information
- Used df.info() to display the DataFrame's structure, including the number of non-null entries and memory usage.

##### Findings:
- The dataset contains 238 rows with mostly complete data, except for a few missing values in the "Screen_Size_inch" and "Weight_kg" columns. This indicates that a small amount of data cleaning may still be necessary before further analysis.

----------------------------------------------------------------------------------------------------------------------------------------------------
## Notebook 2 - Data Wrangling

### Key Skills Covered:
- Handling missing data in different ways
- Correcting incorrect data types
- Standardizing and normalizing dataset attributes
- Visualizing data using binning
- Converting categorical data into numerical indicators

### Setup & Libraries Used:
- pandas (data manipulation)
- numpy (mathematical operations)
- matplotlib (data visualization)
- skillsnetwork (dataset download)

### Key Tasks & Insights:
#### 1. Importing Required Libraries:
- numpy, pandas, and matplotlib are loaded for data processing.

#### 2. Loading the Dataset:
- The dataset is downloaded and loaded into a Pandas DataFrame using pd.read_csv().
- The dataset contains 238 rows and 13 columns, including attributes like Manufacturer, Category, Screen_Size_cm, Weight_kg, and Price.

#### 3. Handling Missing Data:
- Identified missing values in Screen_Size_cm (4 missing values) and Weight_kg (5 missing values).
- Replaced missing Weight_kg values with the mean of the column.

#### 4. Data Type Correction & Standardization:
- Rounded Screen_Size_cm values to two decimal places for consistency.

#### 5. Further Data Processing:
- Future tasks in the lab involve standardizing and normalizing data, visualizing attributes using binning, and converting categorical data into numerical indicators.

----------------------------------------------------------------------------------------------------------------------------------------------------
## Notebook 3 - Exploratory Data Analysis

### Key Skills Covered:

- Visualizing feature patterns

- Running descriptive statistical analysis

- Using groups and pivot tables to analyze categorical variables

- Measuring correlation using Pearson’s method

### Setup & Libraries Used:

pandas, numpy, seaborn, matplotlib, scipy

### Key Tasks & Insights:
#### 1. Visualizing Feature Patterns
Regression Plots for continuous variables (CPU_frequency, Screen_Size_inch, Weight_pounds) vs. Price

##### Findings:

- CPU_frequency has a moderate positive correlation (0.37)

- Screen_Size_inch and Weight_pounds show weak correlations with price

- Box Plots for categorical variables (Category, GPU, OS, CPU_core, RAM_GB, Storage_GB_SSD)

- Differences in median price observed across these categories

#### 2. Descriptive Statistical Analysis
- Summary statistics for numerical and categorical features
- Identified distribution trends and variations in laptop pricing

#### 3. Measuring Correlations
- Used Pearson correlation matrix
- CPU_frequency had the highest positive correlation with price
- Other features had minimal impact

----------------------------------------------------------------------------------------------------------------------------------------------------
## Notebook 4 - Model Development

### Key Skills Covered:
- Implementing Linear Regression with one and multiple variables
- Applying Polynomial Regression to fit data
- Building regression models with pipelines
- Evaluating regression models using Mean Squared Error (MSE) and R-squared (R²)
- Using various regression techniques for predicting outcomes

### Libraries Used:
- pandas: for data manipulation and analysis
- numpy: for mathematical operations
- matplotlib: for visualizations and plotting
- seaborn: for enhanced visualizations
- sklearn: for machine learning and model evaluation (LinearRegression, PolynomialFeatures, StandardScaler, etc.)

### Key Tasks & Insights:
#### 1. Single Linear Regression

##### Steps:
1. Load the dataset and inspect it.
2. Train the Linear Regression model on the "CPU_frequency" feature.
3. Visualize the actual vs. predicted price using distribution plots.
4. Calculate and interpret the Mean Squared Error (MSE) and R-squared score.

##### Outcome:
- MSE and R² values are calculated to evaluate model performance.
- The results give insight into the relationship between CPU frequency and price.

#### 2. Multiple Linear Regression

##### Steps:
1. Train a Multiple Linear Regression model using these features.
2. Visualize the predicted values against the actual values.
3. Evaluate the model using MSE and R².

##### Outcome:
- The performance comparison between Single and Multiple Linear Regression is analyzed, highlighting improvements with more features.

#### 3. Polynomial Regression

##### Steps:
1. Fit polynomial regression models with degrees 1, 3, and 5.
2. Visualize the regression fits on the data using plots.
3. Calculate MSE and R² for each polynomial model.

##### Outcome:
- Insights gained on how polynomial degree impacts the model's ability to fit the data.
- Comparison of polynomial fits with linear models to understand the benefits of higher-degree polynomials in this scenario.

#### 4. Pipeline for Polynomial Regression

##### Steps:
1. Set up a pipeline using PolynomialFeatures, StandardScaler, and LinearRegression.
2. Split the data into training and testing sets.
3. Fit the pipeline on the training data.
4. Use the pipeline to predict the test data and visualize the actual vs. predicted values in a scatter plot.
5. Evaluate the model performance by calculating MSE and R² values.
6. Compare the performance of the pipeline model to previous models (e.g., linear regression and polynomial regression without a pipeline).

##### Outcome:
- The pipeline streamlines the model-building process, reducing the risk of errors in transformation and modeling.
- Insights on the impact of polynomial features and scaling on model performance.
- A comparison of pipeline model performance against other models in terms of accuracy and fit.

----------------------------------------------------------------------------------------------------------------------------------------------------
## Notebook 5 - Model Evaluation and Refinement

### Key Skills Covered
- Data Splitting & Cross-Validation: Used train_test_split() and cross_val_score() to divide data and improve model performance.
- Regression Analysis: Implemented linear and polynomial regression models.
- Overfitting Identification: Analyzed R² scores across polynomial degrees to determine when the model starts to overfit.
- Ridge Regression: Applied Ridge Regression to control overfitting by adjusting the alpha hyperparameter.
- Hyperparameter Tuning with Grid Search: Used GridSearchCV to optimize model performance by finding the best hyperparameter settings.

### Libraries Used
- pandas – Data manipulation and preprocessing
- numpy – Numerical operations
- matplotlib & seaborn – Data visualization
- sklearn – Machine learning tools (regression models, cross-validation, Ridge regression, hyperparameter tuning)

### Key Tasks & Insights
#### 1. Data Preparation & Initial Model Training
- Loaded a dataset of laptop specifications and prices.
- Dropped unnecessary columns and split the dataset into training (90%) and testing (10%) subsets.
- Built a simple linear regression model using "CPU_frequency" as a predictor.
- Found poor performance on test data (negative R² score), suggesting that a single feature is insufficient.

#### 2. Cross-Validation for Model Improvement
- Used 4-fold cross-validation to evaluate model stability.
- Results showed a negative mean R² (-0.161) with high variance, indicating that the model lacks generalization.

#### 3. Overfitting Detection with Polynomial Regression
- Increased model complexity using polynomial features (degrees 1–5).
- Plotted R² scores to visualize performance changes.
- R² initially improves but then drops, highlighting overfitting at higher degrees.

#### 4. Ridge Regression for Overfitting Control
- Used multiple features (CPU frequency, RAM, SSD storage, etc.) in a degree-2 polynomial model.
- Applied Ridge Regression to introduce regularization and control overfitting.
- Evaluated R² scores across different alpha values (0.001 to 1).
- Found an optimal alpha value, demonstrating Ridge Regression’s ability to improve generalization.

#### 5. Hyperparameter Tuning with Grid Search
- Used GridSearchCV to automate hyperparameter selection.
- Identified the best model parameters for improved accuracy
