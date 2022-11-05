# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE

```

'''
Developed By: V.NAVYA
Register No: 212221230069
'''
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()


```

# OUPUT


![image](https://user-images.githubusercontent.com/94165327/200098317-b2363e4a-cfea-487b-b99d-c436ed0c285e.png)



![image](https://user-images.githubusercontent.com/94165327/200098325-8ecd3115-59e0-4c5f-910b-f4d57b563e65.png)


![image](https://user-images.githubusercontent.com/94165327/200098342-4be0b83a-8fab-4742-91da-6ff88597eda7.png)



![image](https://user-images.githubusercontent.com/94165327/200098359-c6e924f7-db7c-44a8-81ef-ab03219d079e.png)



![image](https://user-images.githubusercontent.com/94165327/200098368-566dfecd-097e-439f-807e-468595faf161.png)


![image](https://user-images.githubusercontent.com/94165327/200098381-4ced1208-27bb-4caf-92bc-37a87dcc6dd2.png)


![image](https://user-images.githubusercontent.com/94165327/200098394-d89f952b-38e9-490a-a266-e0264ab398dd.png)


![image](https://user-images.githubusercontent.com/94165327/200098401-110c8c62-4fbc-42d5-b9ff-2be0bdf8fb96.png)


![image](https://user-images.githubusercontent.com/94165327/200098405-689baaef-72c3-4d16-adce-e94fda1c769a.png)


![image](https://user-images.githubusercontent.com/94165327/200098425-51a9b736-00f3-4476-aa3f-678e8c7a976a.png)


![image](https://user-images.githubusercontent.com/94165327/200098432-391ee79f-2b4a-43f5-b212-ab8b78373fec.png)



![image](https://user-images.githubusercontent.com/94165327/200098435-1e64e898-49ea-4d30-a176-046ba5e73146.png)



![image](https://user-images.githubusercontent.com/94165327/200098450-ddcd58a5-2b22-4aca-bed4-99ce2ef365df.png)



# RESULT

Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.

