**Training and Evaluating a Simple Linear Regression Model**

*Introduction*

Linear regression is a supervised learning algorithm used for predictive analysis. The goal is to establish a linear relationship between a dependent variable (target) and one or more independent variables (features).

In this tutorial, we will guide you through training a simple linear regression model and evaluating its performance using Python's scikit-learn library.

*1. Import Required Libraries*

We’ll be using pandas for data handling and scikit-learn for model training and evaluation.

python code :

import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

*2. Load the Dataset*

Load your dataset, ensuring it has clearly defined features (independent variables) and target (dependent variable). For this tutorial, let’s assume we have a CSV file.

python code:

data = pd.read_csv('your_dataset.csv')
X = data[['independent_variable']]  # Independent variable(s)
y = data['dependent_variable']      # Dependent variable (target)
3. Split the Dataset
Use train_test_split to divide the data into training and testing sets. This helps to train the model on one part of the data and evaluate it on another part.

python code:

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
*4. Train the Linear Regression Model*
Initialize the linear regression model and train it using the training data.

python code :

model = LinearRegression()
model.fit(X_train, y_train)

*5. Make Predictions*

After training, use the model to predict the target values for the test set.

python code :

y_pred = model.predict(X_test)

*6. Evaluate the Model*

Evaluate the model’s performance using two key metrics: Mean Squared Error (MSE) and R-squared score.

python code :

mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print(f'Mean Squared Error: {mse}')
print(f'R-squared Score: {r2}')
Mean Squared Error (MSE) tells us how close the predicted values are to the actual values. Lower is better.
R-squared score measures how well the independent variables explain the variance in the dependent variable. Closer to 1 is better.

*7. Conclusion*

This document walks through the complete process of training and evaluating a linear regression model using scikit-learn. You can now further improve the model or experiment with different datasets.

