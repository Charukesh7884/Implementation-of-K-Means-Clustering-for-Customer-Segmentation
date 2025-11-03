# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1. **Data Preprocessing**  
   Load the dataset using pandas and inspect for missing values or incorrect data types.

2. **Optimal Cluster Selection (Elbow Method)**  
   Calculate the Within-Cluster Sum of Squares (WCSS) for cluster counts ranging from 1 to 10 and plot the elbow graph to determine the optimal number of clusters.

3. **Model Training**  
   Apply the K-Means algorithm with the selected number of clusters on features such as *Annual Income* and *Spending Score* to segment customers.

4. **Visualization and Interpretation**  
   Visualize the clustered data using Matplotlib, assigning distinct colors to each cluster to interpret customer segments effectively.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: CHARUKESH S
RegisterNumber:  21224230044
*/
```
```python
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv("Mall_Customers.csv")
df.head(5)

df.info()

df.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
    kmeans=KMeans(n_clusters = i,init='k-means++')
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Cluster")
plt.ylabel("wcss")
plt.title("Elbow Method")
print("Name: CHARUKESH S")
print("Register No: 212224230044")

km=KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])

y_pred=km.predict(df.iloc[:,3:])
y_pred

df["cluster"]=y_pred
df0=df[df["cluster"]==0]
df1=df[df["cluster"]==1]
df2=df[df["cluster"]==2]
df3=df[df["cluster"]==3]
df4=df[df["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
print("Name: CHARUKESH S")
print("Register No: 212224230044")
```

## Output:
<img width="972" height="230" alt="image" src="https://github.com/user-attachments/assets/c2049a26-40e9-473a-88ba-312e4f8df889" />
<img width="956" height="293" alt="image" src="https://github.com/user-attachments/assets/de7e492f-464d-4aea-991f-3ef2a0cad874" />
<img width="966" height="168" alt="image" src="https://github.com/user-attachments/assets/0489cd4c-cf16-451d-91d8-aec7dc83ebde" />
<img width="961" height="650" alt="image" src="https://github.com/user-attachments/assets/5e21decb-b083-49cc-a61f-5dc3fbfd9af7" />
<img width="958" height="107" alt="image" src="https://github.com/user-attachments/assets/62e2ba38-55b1-46f6-b768-0fbb2f351a91" />
<img width="952" height="244" alt="image" src="https://github.com/user-attachments/assets/abda5c3d-b522-49bd-8019-4c94a5d76179" />
<img width="966" height="625" alt="image" src="https://github.com/user-attachments/assets/6aa39587-483d-4546-92e4-eb9e0bf6bff4" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
