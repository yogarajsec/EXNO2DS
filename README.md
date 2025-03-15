# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![Screenshot 2025-03-15 105424](https://github.com/user-attachments/assets/15709f31-e021-4a35-933d-5a632ab0b5ce)
```
dt.info()
```
![Screenshot 2025-03-15 105432](https://github.com/user-attachments/assets/14df70c5-c6c8-42ce-80a9-3c69d02901bc)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![Screenshot 2025-03-15 105438](https://github.com/user-attachments/assets/816d2b45-ce00-4f8a-a768-a078dc97c489)
```
dt.shape
```
![Screenshot 2025-03-15 105447](https://github.com/user-attachments/assets/c84e1e3b-a407-4d61-8899-cf2531c682b7)
```
dt.nunique()
```
![Screenshot 2025-03-15 105453](https://github.com/user-attachments/assets/18aaafa3-5097-4b82-a102-aa6dfe0424d8)
```
dt["Survived"].value_counts()
```
![Screenshot 2025-03-15 105501](https://github.com/user-attachments/assets/28dc7fad-4091-4fcf-8282-3cbc8a0a61e6)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-15 105506](https://github.com/user-attachments/assets/9d430a5e-d973-4017-98e2-6d2504ed10ac)
```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2025-03-15 105511](https://github.com/user-attachments/assets/9162dcdf-ab42-4077-a9ce-4073dd151090)
```
dt.Pclass.unique()
```
![Screenshot 2025-03-15 105517](https://github.com/user-attachments/assets/25827b43-9df1-4144-b8ee-e698c1b423aa)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2025-03-15 105529](https://github.com/user-attachments/assets/98019d60-021b-40d2-b97a-3a50014671fd)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![Screenshot 2025-03-15 105538](https://github.com/user-attachments/assets/9742b48f-2bc8-413e-b2f8-18188c77b3d3)
```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```
![Screenshot 2025-03-15 105547](https://github.com/user-attachments/assets/5592c129-305f-4b8a-a636-378b6dfde1b4)
```
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-15 105553](https://github.com/user-attachments/assets/72db4939-9625-4bee-8bd7-97a4f7de7e68)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![Screenshot 2025-03-15 105559](https://github.com/user-attachments/assets/b4dad5fa-b510-4916-8f6e-a44638786d26)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2025-03-15 105612](https://github.com/user-attachments/assets/2c742097-1b87-4026-a82d-3e266b583616)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![Screenshot 2025-03-15 105618](https://github.com/user-attachments/assets/edbbff3a-253c-4697-b5d0-ceb49c2c7a5b)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-15 105629](https://github.com/user-attachments/assets/263c82b2-1358-41bb-bc4a-88b810032ee4)
```
corr=dt.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2025-03-15 105641](https://github.com/user-attachments/assets/9d3a11ce-5872-440c-8ac8-5cee6b6dfe08)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/0589eaa1-92f9-4f8f-95d2-cca9cd83728a)



# RESULT
Exploratory Data Analysis on the given data set successfully.
        
