# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Detect File Encoding: Use chardet to determine the dataset's encoding.

2.Load Data: Read the dataset with pandas.read_csv using the detected encoding.

3.Inspect Data: Check dataset structure with .info() and missing values with .isnull().sum().

4.Split Data: Extract text (x) and labels (y) and split into training and test sets using train_test_split.

5.Convert Text to Numerical Data: Use CountVectorizer to transform text into a sparse matrix.

6.Train SVM Model: Fit an SVC model on the training data.

7.Predict Labels: Predict test labels using the trained SVM model.

8.Evaluate Model: Calculate and display accuracy with metrics.accuracy_score.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Ramnithish.R 
RegisterNumber: 212224230219 
*/
```
```
import chardet
file='spam.csv'
with open(file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result
```
```
import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')
```
```
data.head()
```
```
data.info()
```
```
data.isnull().sum()
```
```
x=data["v2"].values
```
```
y=data["v1"].values
```
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
```
```
x_train
```
```
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer()
x_train = cv.fit_transform(x_train)
x_test = cv.transform(x_test)
```
```
x_test
```
```
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
```
```
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
<img width="708" height="150" alt="398595784-ba42ca2d-85a5-4795-b40d-63df37236a81" src="https://github.com/user-attachments/assets/066cb921-0d21-4426-a4d0-c9da18093b06" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<img width="726" height="237" alt="398595804-22edcf48-dd25-4513-867d-6c7430da985d" src="https://github.com/user-attachments/assets/eb9a8a43-8cd1-49f1-8411-6a02580f1244" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="414" height="274" alt="398595822-618324db-35cd-4c45-8469-466a22c5cf86" src="https://github.com/user-attachments/assets/18986a92-b54a-47a8-b39d-14d41195c35d" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="220" height="169" alt="398595845-81bc5619-eb01-41f1-9218-e95a64875d42" src="https://github.com/user-attachments/assets/5df833d5-fc44-41f8-866c-0e74076bdfa5" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


<img width="1347" height="238" alt="image" src="https://github.com/user-attachments/assets/a737c9ac-2505-4967-908c-4a89c2a6e1d7" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1340" height="97" alt="Screenshot 2025-10-30 094554" src="https://github.com/user-attachments/assets/7587e9b5-8f09-48d5-93c7-41ac836fb987" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="1347" height="168" alt="image" src="https://github.com/user-attachments/assets/c027507a-00ed-4c3a-80b1-691aaa8b625d" />

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="422" height="131" alt="398595912-3da73419-4d11-45bf-b361-b1fd344e732e" src="https://github.com/user-attachments/assets/8e2cc606-6971-4e5e-8982-ca041094e69d" />

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
