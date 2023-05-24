# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary python packages using import statements.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head()
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print all the outputs.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Yuvadarshini S
RegisterNumber: 212221230126
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.info()

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  
plt.plot(range(1,11),wcss,color="#fc0345")
plt.xlabel("No of Customers")
plt.ylabel("wcss")
plt.title("Elbow method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="#00FE1E",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="#fc0345",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="#03a9fc",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="#fc2503",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="#0345fc",label="cluster4")
plt.legend()
plt.title("Customer Segments")
*/
```

## Output:

![81](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/dd353093-bc8c-49d7-b288-1df4d5ee9ca8)

![82](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/0eca3fae-9bb8-48e5-b146-2367a1370760)

![83](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/8b571275-496d-4574-99d3-1cff0e33f91e)

![84](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/31f407bf-2985-4cde-bb5d-5a807beb6cb7)

![85](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/94b732d7-083f-4f10-b14d-f0a209b8392c)

![86](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/5bbcd5c1-7393-45f4-9b02-159ce485c3b4)

![87](https://github.com/Yuvadarshini-Sathiyamoorthy/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93482485/78768069-2429-41d8-9562-248dfb364dbf)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
