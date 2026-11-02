# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required Python libraries such as Pandas and Scikit-learn.
2. Load the `Placement_Data.csv` dataset using Pandas.
3. Select the academic performance features `ssc_p`, `hsc_p`, `degree_p`, `etest_p`, and `mba_p` as input variables.
4. Select `status` as the target variable.
5. Convert the placement status into numerical values, where `Placed` is represented by 1 and `Not Placed` is represented by 0.
6. Split the dataset into training and testing data.
7. Create a Logistic Regression model.
8. Train the model using the training dataset.
9. Predict the placement status for the test dataset.
10. Calculate the accuracy and confusion matrix of the model.
11. Predict the placement status of a new student using the trained model.
12. Display the prediction and placement probability.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: KIREN SIDDHARTH D
RegisterNumber: 212224250009

import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix

# Load the dataset
data = pd.read_csv("Placement_Data.csv")

# Display the first five records
print("First five records of the dataset:")

print(data.iloc[:, :8].head().to_string())

print("\n", data.iloc[:, 8:].head().to_string())


# Select input features
X = data[
    [
        "ssc_p",
        "hsc_p",
        "degree_p",
        "etest_p",
        "mba_p"
    ]
]

# Select target variable
y = data["status"]

# Convert placement status into numerical values
# Placed = 1
# Not Placed = 0

y = y.map({
    "Placed": 1,
    "Not Placed": 0
})

# Split the dataset into training and testing data
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)

# Create Logistic Regression model
model = LogisticRegression()

# Train the model
model.fit(X_train, y_train)

# Predict placement status
y_pred = model.predict(X_test)

# Calculate accuracy
accuracy = accuracy_score(y_test, y_pred)

# Display actual and predicted values
print("\nActual Placement Status:")
print(y_test.values)

print("\nPredicted Placement Status:")
print(y_pred)

# Display accuracy
print("\nAccuracy:", accuracy)

# Display confusion matrix
print("\nConfusion Matrix:")
print(confusion_matrix(y_test, y_pred))

# Predict placement status for a new student
new_student = pd.DataFrame({
    "ssc_p": [80],
    "hsc_p": [75],
    "degree_p": [78],
    "etest_p": [80],
    "mba_p": [72]
})

# Make prediction
prediction = model.predict(new_student)

# Calculate probability
probability = model.predict_proba(new_student)

print("\nNew Student Details:")
print("SSC Percentage: 80")
print("HSC Percentage: 75")
print("Degree Percentage: 78")
print("E-Test Percentage: 80")
print("MBA Percentage: 72")

# Display placement prediction
if prediction[0] == 1:
    print("\nPredicted Placement Status: Placed")
else:
    print("\nPredicted Placement Status: Not Placed")

print(
    "Placement Probability:",
    probability[0][1]  )
 
*/
```

## Output:
<img width="609" height="609" alt="image" src="https://github.com/user-attachments/assets/0925bfb6-4278-416d-9a1d-ebe72c257e19" />


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
