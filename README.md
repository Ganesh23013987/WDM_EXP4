### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 21/09/2025
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program 1:
```
import pandas as pd
df=pd.read_csv("/content/clustervisitor.csv")
df.head()
cluster={"young":(df['Age']<=30),"Middle":((df['Age']>30)&(df['Age']<=60)),"Old":(df['Age']>50)}
cluster
count=[]
for g,c in cluster.items():
    visitor=df[c]
    count.append(len(visitor))
    print(f"Visitors in {g} group")
    print(visitor)
    print(count)
from sklearn.cluster import KMeans
import matplotlib.pyplot as plt
plt.bar(cluster.keys(),count,data=df)
plt.xlabel('Age Group')
plt.show()
```
### Output:

<img width="850" height="850" alt="image" src="https://github.com/user-attachments/assets/0dcafe14-2307-468c-8bc5-7c13ef540f35" />

### Program 2:

```
kmeans = KMeans(n_clusters=3, random_state=42)
df['Cluster'] = kmeans.fit_predict(df[['Age']])
print(df)
plt.scatter(df['User_ID'], df['Age'], c=df['Cluster'])
plt.xlabel('User_ID')
plt.ylabel('Age')
plt.title('K-Means')
plt.show()
```

### Output:
<img width="850" height="850" alt="image" src="https://github.com/user-attachments/assets/2b840428-0bf9-440e-8cb4-acc72f52abc2" />
<img width="850" height="850" alt="image" src="https://github.com/user-attachments/assets/51d7a4be-61c9-4779-9ea9-042b48e2ae37" />


### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully
