# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: NANDHINI N

RegisterNumber: 212224040212

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

import pandas as pd

import matplotlib.pyplot as plt

data = pd.read_csv('Mall_Customers.csv')

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss = [] #Within-Cluster Sum of Square.

#It is the sum of squared distance between each point & the centroid in a cluster

for i in range(1,11):

     kmeans = KMeans(n_clusters = i, init = "k-means++")
     kmeans.fit(data.iloc[:, 3:])
     wcss.append(kmeans.inertia_)

plt.plot(range(1,11), wcss)

plt.xlabel("Number of Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km = KMeans(n_clusters = 5)

km.fit(data.iloc[:, 3:])

KMeans(n_clusters = 5)

y_pred = km.predict(data.iloc[:, 3:])

y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"] == 0]

df1 = data[data["cluster"] == 1]

df2 = data[data["cluster"] == 2]

df3 = data[data["cluster"] == 3]

df4 = data[data["cluster"] == 4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segments")

## Output:

![Screenshot 2025-05-19 160039](https://github.com/user-attachments/assets/1ef2d593-1e8f-4903-88ab-4e25ea0d5061)

![Screenshot 2025-05-19 160045](https://github.com/user-attachments/assets/cca4fb60-1ae9-44f9-a45c-a2f120eaefb3)

![Screenshot 2025-05-19 160052](https://github.com/user-attachments/assets/fa5cdc90-0018-4729-b616-5ea6e732ce5b)

![Screenshot 2025-05-19 160100](https://github.com/user-attachments/assets/198fc978-8196-4915-9835-7ab749109666)

![Screenshot 2025-05-19 160110](https://github.com/user-attachments/assets/54fa112e-4297-45c8-88e2-7aae65698640)

![Screenshot 2025-05-19 160116](https://github.com/user-attachments/assets/fdbbe0bf-e78f-44d6-8e65-18efeeb60e7a)

![Screenshot 2025-05-19 160124](https://github.com/user-attachments/assets/a01aa678-dd5f-4738-82d2-45758b6c4086)

![Screenshot 2025-05-19 160132](https://github.com/user-attachments/assets/6ef1f7d2-e80c-4c3c-b0fd-cfec0c2d7d96)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
