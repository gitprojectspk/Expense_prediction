# Expense_prediction

Created Model Deployment using Flask and Heroku.

Proposed Approach:

# A: Create and Pickle a Machine Learning Model

I used Income_Expense dataset and created a model using LinearRegression model. This model will predict the expense of the person using income and age as input features.
Please refer to https://bitbucket.org/pk_projects/work/src/week4/expense_prediction.ipynb 

This model performs below operations:
## Step 1 - Import data 
- Explore the data
## Step 2-Data Cleaning:
- Looks for missing values, replaces missing data with appropriate values using imputation technique.
- hecking Outlier by definition and treating outliers
## Step 3- Exploratory data analysis
- Check how Expense is varying with income
- Check how Expense is varying with Age
- Check correlation matrix - to check the strength of variation between two variables
## Step 4-feature engineering
- Normalization/scaling of data - understanding scaling
- Converting data back to pandas dataframe
- Separating features and response
- Dividing data in test and train
- Importing necessary packages
- Fitting linear regression model
- Checking accuracy on test data
- Predict values on test data

## This creates a model that can predict the expense of person with ~68% accuracy.

# B Model Deployment prep:
Model can then be pickled using

## import pickle
pickle.dump(model, open('expense_prediction.pkl','wb'))

## The pickle file can be found inside the same directory as the Jupyter notebook.
https://bitbucket.org/pk_projects/work/src/week4/expense_prediction.pkl

# C Write Flask App:

Using IDE or visual studio code, create a new .py file inside the working directory named app.py. which looks like the snapshot below.
The structure of the code follows:
-	Load pickled model
-	Name flask app
-	Create a route that receives inputs through a html page, uses the trained model to make a prediction, and returns the prediction in a html format, which can be accessed through the API endpoint.
 


The app file uses render_template function to load index.html
Index.html is nothing but a user interface which accepts input variables for income and age and returns expense as output.
This template can be found in
https://bitbucket.org/pk_projects/work/src/week4/templates/index.html

app file further uses predict() function to predict the output.

# D:

Once the app.py file is ready, I ran the flask app from the command line as below
python app.py

I got the following message with the address:
The app can now be tested using url http://127.0.0.1:5000
![image](https://user-images.githubusercontent.com/96436449/195422131-54ba1a0a-d168-42e8-8c15-e124b0992c58.png)

The model predicted 17711 as expense for input variables income =30000 and age = 24.

# E : Create requirements.txt
The requirements.txt file contain all the dependencies for the flask app. This can be created using below command:
pip freeze > requirements.txt

The folder contains below files.
![image](https://user-images.githubusercontent.com/96436449/195422156-30aea62b-366c-4333-bd16-d535e74b6312.png)

 

