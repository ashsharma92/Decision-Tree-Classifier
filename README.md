# Decision-Tree-Classifier
Used python to classify a cars data set to understand if it was made in the US or not.

# Context
This project focuses on building a Decision Tree Classifier to predict the brand origin (US, Europe, or Japan) of cars based on various automotive attributes such as MPG, cylinders, horsepower, weight, and year. Understanding these relationships can be valuable for market analysis, product development, and competitive intelligence within the automotive industry. The goal is to develop a predictive model that accurately classifies car brands using a decision tree algorithm.

# Actions & Techniques Applied
Data Acquisition and Initial Inspection:

The cars.csv dataset was loaded into a pandas DataFrame.

Initial inspection included printing column names and displaying the head of the DataFrame to understand its structure and content.

# Data Cleaning & Preprocessing:

Column Renaming: Column names were stripped of leading/trailing whitespace to ensure consistency and ease of access.

Categorical Data Cleaning: The 'brand' column, initially containing values like 'US.', 'Europe.', 'Japan.', was cleaned by removing the trailing periods using string manipulation methods. Unique values were checked to confirm successful cleaning.

Missing Value Handling:

Numerical feature columns (mpg, cylinders, cubicinches, hp, weightlbs, time-to-60, year) were explicitly converted to numeric types, with non-convertible values coerced to NaN.

Missing values (NaN) introduced during type conversion (specifically in cubicinches and weightlbs) were identified using isnull().sum().

Rows containing any NaN values were dropped from the dataset using dropna() to ensure a clean dataset for model training.

Data Filtering: The cleaned dataset was further filtered to ensure only 'US', 'Europe', and 'Japan' brands were included, preparing the data for binary classification (US vs. non-US).

# Model Setup and Training (Decision Tree):

Feature and Target Definition:

Features (X) included mpg, cylinders, cubicinches, hp, weightlbs, time-to-60, and year.

The target variable (y) was defined as a binary classification: 1 if the brand is 'US', and 0 otherwise.

Train-Test Split: The dataset was split into training and testing sets (80/20 ratio) using train_test_split from sklearn.model_selection to evaluate model performance on unseen data.

# Decision Tree Implementation:

DecisionTreeClassifier from sklearn.tree was used to build the classification model.

Models were trained with varying max_depth parameters (e.g., max_depth=1 and max_depth=2) to observe the impact of tree complexity on classification.

Tree Visualization: plot_tree from sklearn.tree was used to visualize the structure of the trained decision trees, showing the splitting criteria (e.g., X[2] <= 134.5), Gini impurity, sample counts, and value distribution at each node.

# Model Evaluation:

Accuracy Score: The accuracy_score from sklearn.metrics was used to evaluate the performance of the trained decision trees on both the training and testing datasets.

# Results
Cleaned and Prepared Dataset: The project successfully cleaned and preprocessed raw car data, addressing inconsistencies, missing values, and ensuring appropriate data types for machine learning.

Effective Brand Classification: The Decision Tree Classifier demonstrated strong performance in classifying cars by their brand origin (specifically, identifying 'US' cars), with high accuracy scores observed on both training and test sets (e.g., 85.78% training accuracy and 94.23% test accuracy for max_depth=1).

Interpretable Model: Decision trees, being inherently interpretable, provided clear insights into the features driving the brand classification (e.g., cubicinches and year as key splitting criteria).

Foundational Predictive Modeling: The project showcases a robust process for building and evaluating a predictive model using a common machine learning algorithm, demonstrating proficiency in a typical data science workflow.
