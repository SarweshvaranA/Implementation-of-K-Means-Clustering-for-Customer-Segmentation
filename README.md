# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplotlib.pyplot

2.Read the dataset and transform it

3.Import KMeans and fit the data in the model

4.Plot the Cluster graph

## Program:
```python
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data

print(data.head())

print(data.info)

print(data.isnull().sum())

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.show()

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
KMeans(n_clusters=5)
y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="teal",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="black",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="cluster4")
plt.legend()
plt.title("Customer Segments")


```

## Output:
![image](https://github.com/user-attachments/assets/e0465a18-765f-4e36-842e-9223e699757c)

![image](https://github.com/user-attachments/assets/1ebf1a45-03b2-4387-9ff5-9b131c00d9e9)


![image](https://github.com/user-attachments/assets/2b64886e-d374-4733-9df2-c47f1373d227)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
