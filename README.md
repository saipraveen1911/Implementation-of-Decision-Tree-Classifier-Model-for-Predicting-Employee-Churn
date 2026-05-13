# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: SAI PRAVEEN C
RegisterNumber:212225230239
 import pandas as pd
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import confusion_matrix, accuracy_score, classification_report
from sklearn import tree

# ------------------------------
# Step 1: Sample dataset (Expanded slightly for better logic)
# ------------------------------
data = {
    'satisfaction_level': [0.38, 0.80, 0.11, 0.72, 0.37, 0.41, 0.10, 0.92, 0.50, 0.65],
    'last_evaluation': [0.53, 0.86, 0.88, 0.87, 0.52, 0.50, 0.77, 0.89, 0.60, 0.70],
    'number_project': [2, 5, 7, 5, 2, 2, 6, 5, 3, 4],
    'average_monthly_hours': [157, 262, 272, 223, 159, 153, 247, 224, 180, 200],
    'time_spend_company': [3, 6, 4, 5, 3, 3, 4, 5, 3, 4],
    'Work_accident': [0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    'promotion_last_5years': [0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    'Departments': ['sales','accounting','hr','technical','support','management','marketing','product','sales','support'],
    'salary': ['low','medium','medium','high','low','low','medium','high', 'low', 'medium'],
    'left': [1, 1, 1, 1, 1, 0, 1, 0, 0, 0] 
}

df = pd.DataFrame(data)

# ------------------------------
# Step 2: Encode categorical variables
# ------------------------------
df = pd.get_dummies(df, columns=['Departments','salary'], drop_first=True)

# ------------------------------
# Step 3: Split into features and target
# ------------------------------
X = df.drop('left', axis=1)
y = df['left']

# ------------------------------
# Step 4: Train-test split 
# Added 'stratify=y' to ensure both sets have 0s and 1s
# ------------------------------
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.3, random_state=42, stratify=y
)

# ------------------------------
# Step 5: Create Decision Tree Classifier
# ------------------------------
dt_model = DecisionTreeClassifier(criterion='entropy', max_depth=4, random_state=42)
dt_model.fit(X_train, y_train)

# ------------------------------
# Step 6: Make predictions
# ------------------------------
y_pred = dt_model.predict(X_test)

# ------------------------------
# Step 7: Evaluate the model
# Added 'zero_division=0' to silence the warning
# ------------------------------
print("Confusion Matrix:\n", confusion_matrix(y_test, y_pred))
print("\nAccuracy Score:", accuracy_score(y_test, y_pred))
print("\nClassification Report:\n", classification_report(y_test, y_pred, zero_division=0))

# ------------------------------
# Step 8: Visualize the decision tree
# ------------------------------
plt.figure(figsize=(12,8))
tree.plot_tree(
    dt_model, 
    feature_names=X.columns.tolist(), 
    class_names=['Stayed','Churn'], 
    filled=True, 
    rounded=True
)
plt.title("Decision Tree for Employee Churn")
plt.show()
*/
```

## Output:
![decision tree classifier model](sam.png)


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
