# <p align="center"> Capstone-Project-on-Insurance-Claims </p>

# <p align="center">![image](https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/assets/96239993/70b59c6c-3693-4015-a3e2-2bcfb5e48f69)</p>


## Overview

Machine learning in insurance claim analysis involves employing algorithms to analyze claim data. 
These algorithms detect fraudulent claims by identifying irregular patterns and behaviors. 
They also assess risk levels associated with claims, predict claim severity, and estimate claim frequency based on historical data and relevant factors. 
By leveraging machine learning, insurers can make data-driven decisions, improving efficiency, reducing costs, and effectively managing risk. 
This enables insurers to streamline the claims process, detect fraudulent activities, and allocate resources more efficiently, ultimately benefiting both insurance companies and policyholders.


  ## Requirements

- Python 3

- Libraries: NumPy, pandas, Sklearn, etc.

- Jupyter Lab

[Datasets Used]
[Claims1.csv](https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/blob/3d49eed36dad710952b5249aacd6ed8b6b247855/Claims1.csv)

https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/blob/529c75ae951b6db47dacdb30915903cacea57d60/cust_demographics%20(1).xlsx

[Python Script (Code)][(Capstone Project_Insurance Claims (1).ipynb)](https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/blob/ddbe97d81046d1eeb5b3c632fc3e9c354ebd215a/Capstone%20Project_Insurance%20Claims%20(1).ipynb)


[Ppt presentation]([Capstone project ppt.pptx](https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/blob/d9a6037c3d70f74831c65d83adbe3fc15c0d69a0/Capstone%20project%20ppt.pptx))


### Features 

- Data preprocessing: Clean and prepare the transactional data for analysis.
  
- Supervised learning: Train classification models to classify transactions as fraudulent or legitimate.
  
- Model evaluation: Assess the performance of the models using relevant metrics such as precision, recall, and F1-score.


## Balancing an unbalanced dataset:
```py
import matplotlib.pyplot as plt
plt.figure(figsize = (3,3))
Cust_data["fraudulent"].value_counts().plot(kind="bar",color=["red","green"])
```
```py
import matplotlib.pyplot as plt
fig = plt.figure(figsize = (3,3))
balanced_sample.fraudulent.value_counts().plot(kind='bar', color= ['red','green'])
plt.title('Distribution of data based on the Fraudulent of our balanced dataset')
plt.show()
```

###### Result: 

![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/acf581f1-9322-4448-ab43-de832070a2ce)

## Model evaluation:
#### Logistic Regression Algorithm
```py
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, classification_report

model = LogisticRegression()
model.fit(x_train, y_train)
train_pred_logi=model.predict(x_train)
LogisticRegression_Train_Accuracy = accuracy_score(train_pred_logi,y_train)
print(LogisticRegression_Train_Accuracy)
print(classification_report(train_pred_logi,y_train))
```
```py
#creating list for train test accuracy
train_test = ['Train','Test']
aucc = [LogisticRegression_Train_Accuracy,LogisticRegression_Test_Accuracy] 
plt.figure(figsize=(3, 3))
# Plot the bar graph
bars = plt.bar(train_test, aucc, color=['red', 'blue'])
#Add Labels and title 
plt.xlabel('Logistic Regression')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison for Train & Test')
#Show the plot
plt.show()
```

###### Result:

![image](https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/assets/96239993/dbe43900-e056-4186-b878-fd3412818816)


#### Building A Decision Tree Classifier plot 

```py
#8. building model using  decision trees classifier 
import matplotlib.pyplot as plt
from  sklearn.tree import plot_tree
plt.figure(figsize=(20,10))
plot_tree(ds,feature_names=x.columns.tolist(),class_names=["0","1"],filled=True)
plt.show()
```

###### Result:

![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/5d4f1929-7dbd-49e1-812b-66bf9a8c8409)




### Random Forest classifier Model
```py
rfr=RandomForestClassifier(n_estimators=9,max_depth=5,random_state=42)
rfr.fit(x_train,y_train)
test_pred_rf=rfr.predict(x_test)
train_pred_rf=rfr.predict(x_train)
print(accuracy_score(train_pred_rf,y_train))
print(accuracy_score(test_pred_rf,y_test))
test_aucc=accuracy_score(test_pred_rf,y_test)
rf_aucc=accuracy_score(train_pred_rf,y_train)
```
```py
#creating list for train test accuracy
train_test = ['Train','test']
aucc = [rf_aucc,dt_test] 
plt.figure(figsize=(8, 4))
# Plot the bar graph
bars = plt.bar(train_test, aucc, color=['green', 'skyblue'])
#Add Labels and title 
plt.xlabel('Random Forest')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison for train test accuracy')
#Show the plot
plt.show()
```

###### Result:
![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/c3969bb8-35d4-4181-bfb1-441b8fcf7ac6)


### Logistic Regression Model

```py
model = LogisticRegression()
model.fit(x_train, y_train)
train_pred_logi=model.predict(x_train)
test_pred_logi = model.predict(x_test)
print(accuracy_score(train_pred_logi,y_train))
lr_aucc=accuracy_score(train_pred_logi,y_train)
print(accuracy_score(test_pred_logi,y_test))
print(accuracy_score(test_pred_logi,y_test))
lr_test=accuracy_score(test_pred_logi,y_test)
```
```py
#creating list for train test accuracy
train_test = ['Train','Test']
aucc = [lr_aucc,lr_test] 
plt.figure(figsize=(8, 4))
# Plot the bar graph
bars = plt.bar(train_test, aucc, color=['green', 'skyblue'])
#Add Labels and title 
plt.xlabel('Logistic Regrassion')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison for Train Test')
#Show the plot
plt.show()
```

###### Result:
![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/a5d63af0-59a1-4809-8a6a-8d0d0817a91c)


### K-Nearest Neighbour Model 
 
```py
“K-Nearest Neighbour
scaler = StandardScaler()
x_train_scaled = scaler.fit_transform(x_train)
x_test_scaled = scaler.transform(x_test)
knn_model = KNeighborsClassifier(n_neighbors=5)
# Fit the model to your training data
knn_model.fit(x_train_scaled, y_train)
# Predict labels for test data
test_pred_knn = knn_model.predict(x_test_scaled)
train_pred_knn = knn_model.predict(x_train_scaled)
print(accuracy_score(train_pred_knn,y_train))
knn_aucc=accuracy_score(train_pred_knn,y_train)
print(accuracy_score(test_pred_knn,y_test))
knn_test=accuracy_score(test_pred_knn,y_test)
```
```py
#creating list for train test accuracy
train_test = ['Train','Test']
aucc = [knn_aucc,knn_test] 
plt.figure(figsize=(8, 4))
# Plot the bar graph
bars = plt.bar(train_test, aucc, color=['green', 'skyblue'])
#Add Labels and title 
plt.xlabel('KNN')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison for Train Test')
#Show the plot
plt.show()
```

###### Result:

![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/b89dc7b8-5c4f-4fcc-8ce1-c6302dba3ce1)


### Naive Bayes Model

```py
gnb = GaussianNB()
# fit the model
gnb.fit(x_train, y_train)
y_train_pred = gnb.predict(x_train)
y_train_pred = pd.Series(y_train_pred)
Model_data_train = pd.DataFrame(y_train)
Model_data_train.shape
Model_data_train['y_pred'] = y_train_pred
print('model accuracy-->{0:0.3f}'.format(accuracy_score(y_train,y_train_pred)))
naive_aucc=accuracy_score(y_train,y_train_pred)
# Data validation on x_test
test_pred_naive=gnb.predict(x_test)
print(accuracy_score(test_pred_naive,y_test))
naive_test=accuracy_score(test_pred_naive,y_test)

from sklearn.metrics import confusion_matrix

data_table = confusion_matrix(y_train, y_train_pred)

print('Confusion matrix\n\n', data_table)

print('\nTrue Positives(TP) = ', data_table[0,0])

print('\nTrue Negatives(TN) = ', data_table[1,1])

print('\nFalse Positives(FP) = ', data_table[0,1])

print('\nFalse Negatives(FN) = ', data_table[1,0])
data_table.shape
```

###### Result:
##### Confusion Matrix:

![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/69fbd392-7a2c-461e-be2f-cd1b1d11e46a)

##### Ploting Confusion Matrix Using Heat Map
```py
matrix = pd.DataFrame(data=data_table, columns=['Actual Positive:1', 'Actual Negative:0'], 
                                 index=['Predict Positive:1', 'Predict Negative:0'])

sns.heatmap(matrix, annot=True, fmt='d', cmap='YlGnBu')
```
###### Result:

![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/ed76c0a6-2220-401a-ac77-9bb3451f0347)

```py
#creating list for train test accuracy
train_test = ['Train','Test']
aucc = [naive_aucc,naive_test] 
plt.figure(figsize=(8, 4))
# Plot the bar graph
bars = plt.bar(train_test, aucc, color=['green', 'skyblue'])
#Add Labels and title 
plt.xlabel('Naive Bayes')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison for Train Test Accuracy')
#Show the plot
plt.show()
```
###### Result:

![image](https://github.com/AhamedSahil/CYBER-SECURITY-/assets/164605797/37214d65-7a7e-414f-99e8-559f9711e0cf)



##### Compariosion of All The Accuracy of Each Model

```py
models = ['LogisticRegression', 'DecisionTreeClassifier','RandomForestClassifier', 'KNeighborsClassifier', 'GaussianNB',] 
accuracy_values = [LogisticRegression_Train_Accuracy, DecisionTreeClassifier_Train_Accuracy,RandomForestClassifier_Train_Accuracy, KNeighborsClassifier_Train_Accuracy, GaussianNB_Train_Accuracy] 
plt.figure(figsize=(18, 5))
# # Plot the bar graph
bars = plt.bar (models, accuracy_values, color=['red', 'blue', 'green', 'orange','black'])
#Add accuracy values on top of each bar
plt.bar_label(bars, labels=[f"{acc:.2f}" for acc in accuracy_values])
#Add Labels and title
plt.xlabel('Models')
plt.ylabel('Accuracy')
plt.title('Accuracy Comparison for Different Models')
#Show the plot
plt.show()
```

###### Result:

![image](https://github.com/manojgaikwad13/Capstone-Project-on-Insurance-Claims/assets/96239993/88af7d20-36f7-4b1f-b5f6-19ae2efe5cae)


