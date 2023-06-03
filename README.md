# Ex-04-Multivariate-Analysis
AIM:
To perform Multivariate EDA on the given data set.

EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:
STEP 1
Import the built libraries required to perform EDA and outlier removal.

STEP 2
Read the given csv file.

STEP 3
Convert the file into a dataframe and get information of the data.

STEP 4
Return the objects containing counts of unique values using (value_counts()).

STEP 5
Plot the counts in the form of Histogram or Bar Graph.

STEP 6
Use seaborn the bar graph comparison of data can be viewed.

STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

STEP 8
Save the final data set into the file.

PROGRAM:

NAME:Dhivyapriya .R

REG NO:212222230032

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

data=pd.read_csv("SuperStore.csv")

data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])

data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Category'],data=data)

states=data.loc[:,["Region","Sales"]] 

states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 

plt.figure(figsize=(17,7)) 

sns.barplot(x=states.index,y="Sales",data=states) 

plt.xticks(rotation = 90) 

plt.xlabel=("REGION")

plt.ylabel=("SALES") 

plt.show()

states=data.loc[:,["State","Sales"]] 

states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 

plt.figure(figsize=(17,7)) 

sns.barplot(x=states.index,y="Sales",data=states) 

plt.xticks(rotation = 90) 

plt.xlabel=("SALES") 

plt.ylabel=("STATES") 

plt.show()

states=data.loc[:,["Category","Sales"]] 

states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 

plt.figure(figsize=(10,7)) 

sns.barplot(x=states.index,y="Sales",data=states) 

plt.xticks(rotation = 90) 

plt.xlabel=("CATEGORY") 

plt.ylabel=("SALES") 

plt.show()

data.corr()

sns.heatmap(data.corr(),annot=True)

OUTPUT:
import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

data=pd.read_csv("/content/SuperStore (1).csv")

data
![Screenshot (56)](https://user-images.githubusercontent.com/119477552/235592379-2ba6b816-0f96-4d2c-8fbf-cfd830ea29cc.png)

data.head()
![Screenshot (57)](https://user-images.githubusercontent.com/119477552/235592423-f71e3ffc-1141-452f-97c4-5e38edac390c.png)

data.info()
![Screenshot (58)](https://user-images.githubusercontent.com/119477552/235592467-53477298-0639-444a-997b-6a74cdf3974e.png)

data.describe()
![Screenshot (59)](https://user-images.githubusercontent.com/119477552/235592539-74200b8e-72bb-4ddd-8518-32a5ac0e7a98.png)

data.dtypes
![Screenshot (60)](https://user-images.githubusercontent.com/119477552/235592625-faf98632-c9f6-4dd8-a10c-824084770969.png)

data.isnull().sum()
![Screenshot (61)](https://user-images.githubusercontent.com/119477552/235592705-6fa444fb-2626-44f9-a700-b867e5f5b027.png)

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])

data.isnull().sum()
![Screenshot (62)](https://user-images.githubusercontent.com/119477552/235592739-9bdcfc07-b8d0-4577-86e6-1b31b3880ca2.png)

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)
![Screenshot (63)](https://user-images.githubusercontent.com/119477552/235592768-5b6728dd-e43d-40da-bb44-f9537316887e.png)

states=data.loc[:,["Region","Sales"]]

states=states.groupby(by=["Region"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("REGION")

plt.ylabel=("SALES")

plt.show()
![Screenshot (64)](https://user-images.githubusercontent.com/119477552/235592803-8c45e31c-a0a0-4d91-b8d8-1b095d0a3f00.png)

states=data.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SALES")

plt.ylabel=("STATES")

plt.show()
![Screenshot (65)](https://user-images.githubusercontent.com/119477552/235592839-0d0573d8-9636-4b4e-9868-7c0cd7d274d4.png)

states=data.loc[:,["Category","Sales"]]

states=states.groupby(by=["Category"]).sum().sort_values(by="Sales")

plt.figure(figsize=(10,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("CATEGORY")

plt.ylabel=("SALES")

plt.show()
![Screenshot (66)](https://user-images.githubusercontent.com/119477552/235592869-c006f158-e3d2-4117-8d56-ed4829e45c54.png)

states=data.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

plt.figure(figsize=(10,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("SALES")

plt.show()
![Screenshot (67)](https://user-images.githubusercontent.com/119477552/235592902-f81f77b4-c4d8-4706-9837-246ef581e84a.png)

data.corr()
![Screenshot (68)](https://user-images.githubusercontent.com/119477552/235592974-973203ed-4949-4dba-96d4-264ec64446fb.png)
![Screenshot (71)](https://user-images.githubusercontent.com/119477552/235593054-099f13a0-d21a-4bb7-a4d3-9fb83a5d5271.png)
sns.heatmap(data.corr(),annot=True)

![Screenshot (72)](https://user-images.githubusercontent.com/119477552/235593079-140e7823-47af-455a-9f3d-c130952c6982.png)

RESULT

Thus the Multivariate EDA is performed on the given data set.

