# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Thiyagarajan A
RegisterNumber:  212222240110
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
### data.head()

![279732903-57ff5af0-e941-48a1-818a-c4f619470a51](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/72431093-9971-4639-9eda-608a1a2552ad)
### data.info()

![279733031-33d766f4-6481-462c-a2b6-5fd0a3416dae](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/a6821907-23aa-4738-92c7-5118e0538e1f)
### data.isnull().sum()


![279733213-4c13171b-b59e-40c0-9f26-38361f9dd1fd](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/27405625-c9df-407e-9d7f-f5fb9b4320fa)

### Elbow method graph

![279733322-82c5a406-5a01-41c4-9fd5-040696498e0d](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/76340581-22fc-416b-a3fe-91a852aef4e8)
### KMeans clusters

![279733399-d0d08318-23ad-47ae-88d0-44566ab5e745](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/a4f1054a-6c8d-4c38-a558-d684583f41b8)
### y_pred

![279733533-eecae550-4062-4d7e-801d-4a03c18b9b24](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/c313cad4-2c38-427c-8868-19e39006f02c)
### Customers Segments Graph

![279733666-4e075d51-0685-40b6-9f76-050b6b1a4c24](https://github.com/A-Thiyagarajan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707693/126ed9d2-054c-429e-b34d-3bd930b94202)







## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
