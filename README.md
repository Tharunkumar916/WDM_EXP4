### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 22.05.2026
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

### Program:
```python

import pandas as pd
df=pd.read_csv('/content/clustervisitor.csv')
print(df)
cluster={"Young":(df['Age']<=30),"Middle":((df['Age']>30) & (df['Age']<=50)),"Old":(df['Age']>50)}
count=[]
for group,condition in cluster.items():
  visitors=df[condition]
  count.append(len(visitors))
  print(f"The visitors on {group} are :")
  print(visitors)
  print("count=",len(visitors))

```
### Output:
<img width="917" height="840" alt="image" src="https://github.com/user-attachments/assets/9e953bd7-76bb-4297-a42a-04881fceff71" />


### Visualization:
```python
import matplotlib.pyplot as plt
plt.figure(figsize=(8,6))
plt.bar(['Young','Middle','Old'],count,color="skyblue")
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title("Visitor Distribution Across Age Groups")
plt.show()
```
### Output:
<img width="695" height="461" alt="image" src="https://github.com/user-attachments/assets/9a355cf4-fd7b-485b-8909-f2148734a3e5" />



### Result:
Thus, visitor segmentation based on age groups was successfully done using Python.
