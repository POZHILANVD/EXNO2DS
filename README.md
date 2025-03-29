# EX.NO.2-Exploratory Data Analysis
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

#### NAME: POZHILAN V D
#### REG.NO:212223240118
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/89a14d3f-8047-4078-b661-81386a14bf92)

```
df.info()
```
![image](https://github.com/user-attachments/assets/0edb0b46-8105-4c81-9827-b850de1fb4ea)

```
df.shape
```
![image](https://github.com/user-attachments/assets/1031205e-2b01-4acc-a78c-5a7ce3a53de0)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/bd1a4f20-ea82-43e8-bf61-81ee0b57f0e0)

```
df.shape
```
![image](https://github.com/user-attachments/assets/7ff52135-128a-4708-b40d-4010f1e1ab18)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/77df6ea0-ee03-4a40-89f1-cd3b9b064f74)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/8fe4274a-8051-4564-a4ec-95935a54ae31)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/7c75b502-3941-4198-81ad-dba75852fb17)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/cdbba011-079b-4594-b9c7-4d6030b9db07)

```
sns.countplot(data=df,x="Survived",color='violet')
```
![image](https://github.com/user-attachments/assets/00da75b9-8cd2-4a16-8ecd-71ac641adec6)

```
df
```
![image](https://github.com/user-attachments/assets/6654858c-370b-4b13-999b-bcc099b55616)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/6a01909a-e76a-4ce8-9bae-720f01e10ff1)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/e2732779-38af-4b6c-be4a-d3eb7a236dc6)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/97fb114e-796e-42d6-a234-1f4b4c011ab0)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/a1192dcd-6a01-4ebc-b446-f8fe51fdfda1)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/e65d3a43-71c7-4cc9-a914-2cd0f3f605df)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/34aed456-93ac-4743-9aca-06b4c687c44d)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/f3e13d47-1b77-4deb-920a-520d9483beeb)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/25ff1e7c-183b-4a4a-934c-c7f9da8ceb01)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/f3047fd3-f949-401d-b76e-bc4deec4dbb3)

```
corr = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/abdacfde-6fdf-4f15-a24c-a56f2f4280ba)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/127d1c2b-948d-4001-b358-dc7140364ba1)

# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.

