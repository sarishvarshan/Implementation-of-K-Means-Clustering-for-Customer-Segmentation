# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import libraries
2.Read the csv file
3'Predict the accuracy
4.End the program 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Sarish Varshan V
RegisterNumber: 212223230196 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("C:/Users/admin/Desktop/Mall_Customers.csv")
data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customers Segments")
```


## Output:
## data.head()
![image](https://github.com/sarishvarshan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152167665/30aaa987-9904-46b0-9824-6aba99397f7c)
## data.info()
![image](https://github.com/sarishvarshan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152167665/5d27f9a8-de55-444a-aa81-7fae6a7e6b85)
## data.isnull.sum()
![image](https://github.com/sarishvarshan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152167665/bc52a28d-046c-4d10-b60a-0571ee5ec782)
## Elbow Method Graph()
![image](https://github.com/sarishvarshan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152167665/82cd106a-d86f-493b-aeb3-748e00af3ce8)
## KMeans Cluster
![image](https://github.com/sarishvarshan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152167665/b4abe496-5745-469e-86f8-45320b21e3d2)
## Customer Segment Graph
![image](https://github.com/sarishvarshan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152167665/90b83396-2eef-40c8-8252-08f23e3e0308)









## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
