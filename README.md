# Supervised Machine Learning - Predicting Credit Risk

## Background

---

LendingClub is a peer-to-peer lending services company that allows individual investors to partially fund personal loans as well as buy and sell notes backing the loans on a secondary market. LendingClub offers their previous data through an API.

Based on this data, create machine learning models to classify the risk level of given loans. Specifically, compare the Logistic Regression model and Random Forest Classifier.

---

## Process

---

### Step 1: Retrieve the data

- Use an entire year's worth of data (2019) to predict the credit risk of loans from the first quarter of the next year (2020). The data is provided in two CSVs:

  - `2019loans.csv`
  - `2020Q1loans.csv`

### Step 2: Preprocessing: Convert categorical data to numeric

- Create a training set from the 2019 loans using `pd.get_dummies()` to convert the categorical data to numeric columns.
- Similarly, create a testing set from the 2020 loans, also using `pd.get_dummies()`.

- Note: There are categories in the 2019 loans that do not exist in the 2020 testing set. If fitting the model to the training set and try to score it on the testing set as is, there will be an error. We need to use code to fill in the missing categories in the testing set before going to the next step.

### Step 3: Consider the models

- Create and compare two models on this data: a logistic regression, and a random forests classifier. Before creating, fitting and scoring the models, make a prediction as to which model we think will perform better.
- Prediction:
  - The logistic regression model wouldn't work well with our data, it's because it needs normal distribution data to work well.
  - In contrast, the Random forest model would work better before the data is scaled.

### Step 4: Fit a LogisticRegression model and a RandomForestClassifier model

- Create a LogisticRegression model, fit it to the data, and print the model's score. Do the same for a RandomForestClassifier.
- Compare two models and confirm which one performed better. Also, check how the final results compare to the prediction.

### Step 5: Revisit the Preprocessing - Scale the data

- The data going into these models was never scaled, an important step in preprocessing. Use `StandardScaler` to scale the training and testing sets.
- Before re-fitting the LogisticRegression and RandomForestClassifier models on the scaled data, make another prediction about how scaling will affect the accuracy of the models.
- Prediction:

  - It's believed that the logistic regression model will work better after the data is scaled, since standardizing is making the data into normal distribution, which works well with logistic model.

- Finally, fit and score the LogisticRegression and RandomForestClassifier models on the scaled data. Confirm how the model scores compare to each other, and to the previous results on unscaled data. Compare final results with the prediction.

## Final Results/Summary:

- It is observed that the Random Forest Model score stays around 0.63~0.64 before and after the data is scaled.
- In contrast, the score for the Logistic Model improves a lot from 0.5168013611229264 to 0.767333049766057.
- Based on the comparison, we can confirm that the score has improved by scaling the data, which is having the data being normally distributed.

---

### References:

- LendingClub (2019-2020) _Loan Stats_. Retrieved from: [https://resources.lendingclub.com/](https://resources.lendingclub.com/)

---

## Thank you!
