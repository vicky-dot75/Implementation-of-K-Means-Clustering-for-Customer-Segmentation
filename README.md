# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and preprocess data: Import data, inspect it, and handle missing values if any.
2. Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.
3. Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.
4. Assign cluster labels to each data point.
5. Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: vignesh s
RegisterNumber: 25014344

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()

data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters=5, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]


```
## output:

<img width="592" height="221" alt="Screenshot 2025-12-11 084222" src="https://github.com/user-attachments/assets/a3b8cb50-0776-4fff-8dc8-4e85ae97694c" />

<img width="530" height="274" alt="Screenshot 2025-12-11 084229" src="https://github.com/user-attachments/assets/a419cfe7-c08a-451c-a7fd-e2b7178d1f88" />

<img width="305" height="158" alt="Screenshot 2025-12-11 084234" src="https://github.com/user-attachments/assets/4ddf4b64-99b0-46a0-ae8c-adb5a5192739" />


<img width="789" height="618" alt="Screenshot 2025-12-11 084251" src="https://github.com/user-attachments/assets/409bfd0c-c2aa-4b5f-86ac-2091e42aa9c0" />

<img width="738" height="239" alt="Screenshot 2025-12-11 084300" src="https://github.com/user-attachments/assets/b76515c6-5ee0-4db1-b353-248ba08bb769" />


<img width="754" height="595" alt="Screenshot 2025-12-11 084308" src="https://github.com/user-attachments/assets/29e5d30e-1a62-4a6c-be20-28698605f00d" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
