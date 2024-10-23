# ML_Zoomcamp-Hmwk-4
Homework Assignment: Bank Marketing Dataset Analysis

This assignment focuses on analyzing the Bank Marketing dataset to predict if a client will subscribe to a term deposit. The task involves using logistic regression and evaluating the model's performance using metrics like ROC AUC, precision, recall, and F1 score. Additionally, hyperparameter tuning is performed with cross-validation.

Dataset Information: 
The dataset used is the Bank Marketing dataset from the UCI Machine Learning Repository. The target variable is y, which indicates whether the client subscribed to a term deposit.

Download and Extract the Dataset:
You can download the dataset and extract it using the following commands:

bash
Copy code
wget https://archive.ics.uci.edu/static/public/222/bank+marketing.zip
unzip bank+marketing.zip
unzip bank.zip
The file we are using is bank-full.csv.

Task Overview
Dataset Preparation:
Selected columns for the analysis:
age, job, marital, education, balance, housing, contact, day, month, duration, campaign, pdays, previous, poutcome, y
Train/Validation/Test Split:
60% train, 20% validation, 20% test using train_test_split with random_state=1.

Questions:
1. ROC AUC Feature Importance:
Compute ROC AUC for each numerical variable (balance, day, duration, previous) using the training dataset.
If AUC is < 0.5, invert the variable by negating it.
Determine which variable has the highest AUC.
Training the Model:

2. Apply one-hot encoding using DictVectorizer.
Train a logistic regression model with LogisticRegression(solver='liblinear', C=1.0, max_iter=1000).
Evaluate the AUC on the validation dataset and round to 3 digits.
Precision and Recall:

3. Compute precision and recall for the model at different thresholds from 0.0 to 1.0 (step 0.01).
Determine the threshold where the precision and recall curves intersect.
F1 Score:

4. Compute F1 score for thresholds from 0.0 to 1.0 (increment 0.01).
Find the threshold at which F1 is maximal.
5-Fold Cross-Validation:

5. Use the KFold class for 5-fold cross-validation.
Train the model on different folds and compute the AUC for validation.
Calculate the standard deviation of the AUC scores across the folds.
Hyperparameter Tuning:

6. Use 5-fold cross-validation to find the best C value from [0.000001, 0.001, 1].
Compute the mean and standard deviation of AUC scores for each C.
Select the best C based on mean AUC, with ties broken by the lowest standard deviation or smallest C.
