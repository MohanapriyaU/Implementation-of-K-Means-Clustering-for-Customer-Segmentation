# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 
RegisterNumber:  
*/
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

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

plt.title("Customer Segment")


## Output:
![K Means Clustering for Customer Segmentation](sam.png)

1.DATA.HEAD():

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/68a26803-f3f0-4630-b159-d91df7f5df60)

2.DATA>INFO():

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/58b7b5d7-b218-4611-9ec8-d835a15b8ed6)

3.DATA.ISNULL().SUM()

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/18433df9-7cd2-4a08-bc7b-4e1b9c94d2c8)

4.PLOT USING ELBOW METHOD:

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/fec3a55f-fb0e-493c-9a7b-2703994a4e01)

5.K-MEANS CLUSTERING

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/788e2392-92c9-455c-bb5c-e26416034d89)

6.Y_PRED ARRAY:

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/d05f7e77-984b-4b16-8e12-735f0dad861a)

7.CUSTOMER SEGMENT

![image](https://github.com/MohanapriyaU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/116153626/f6f4559c-c24c-465e-be42-ed1fd380305e)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
