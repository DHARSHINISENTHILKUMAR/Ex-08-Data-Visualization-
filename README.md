# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

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
~~~
#Reading the given dataset

import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line Plot

plt.figure(figsize=(9,6))
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

#4.Violin Plot

sns.violinplot(x="Profit",data=df)

#5.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#6.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#7.Count plot

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)

#8.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#9.KDE Plot

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
~~~
# OUPUT
## Reading the given dataset
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/65cd2728-d91d-40df-a92f-76809a41e8eb)
## Data Visualization Using Seaborn:
### 1.Line Plot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/394e4a7b-c308-496e-a09b-2b1485f5aea0)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/86307d8c-22fb-42e9-9e36-2db844d2b9dc)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/665d02f5-2a53-4646-88fd-c65b92e2b05f)
### 2.Scatterplot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/60359684-a08e-402f-a4ef-a1a47d336412)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/ec6a3ad3-d91f-4b87-a0af-480b9054cb5c)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/525d063a-67a9-4eb3-bbd4-98100ae635d7)
### 3.Boxplot:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/3cb10ebb-ad27-4f53-97c9-a6263294b3a7)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/60dcfc2e-b362-40cc-a3c9-8a5af629b5ce)
### 4.Violin Plot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/415939e5-13a2-4636-adea-5fb3f00f15e5)
### 5.Barplot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/814c8c73-3432-4408-b5a9-4398d86b23fe)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/db32d3ea-8227-46da-96aa-5a0bbb821691)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/6732040c-cd2f-40c7-8bd8-d6d91aaf561f)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/47da793e-f217-49fb-bfd0-c8c1c6cd7af4)
### 6.Pointplot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/29ef020a-5b5e-49b0-8198-17c7dec84d6d)
### 7.Count plot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/6b92ec00-d694-4321-9a69-ee9bd8750544)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/8082d5cc-53e5-4d6b-9cc6-bbd40200eed1)
### 8.Histogram
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/1fd81c2b-3088-4c30-9659-816aa3c149ef)
### 9.KDE Plot
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/3ef3cb9c-27f9-4cc5-84e6-d655aecc9cef)
## Data Visualization Using Matplotlib:
### 1.Plot:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/11dc39c6-6301-49da-9626-b0f7903c24be)
### 2.Heatmap:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/e73f13c8-bdba-4fbc-907e-38b6204042cc)
### 3.Piechart:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/afa571b5-f4d5-4a9d-93f6-23b1a400be9e)
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/8f63d680-cf6b-41ea-8d3d-e176258656c7)
### 4.Histogram:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/4c95e841-f3ae-4349-ae91-c8277aab743a)
### 5.Bargraph:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/67e02359-a34c-4f5c-91c2-e4ea6b3d13b7)
### 6.Scatterplot:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/dc78a83e-ebcc-436f-82aa-a6c43c1fed18)
### 7.Boxplot:
![image](https://github.com/DHARSHINISENTHILKUMAR/Ex-08-Data-Visualization-/assets/113699377/8ddff1a9-666a-4eb7-bdc6-7226d1586a26)
# Result:
~~~
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
~~~
