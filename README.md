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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/a8e04567-43d4-4d56-b5a4-87df60449cb3)

```
df.info()
```
![image](https://github.com/user-attachments/assets/99b204c8-d7e0-437b-8aff-f9ef0bb9be0d)

```
df.shape
```
![image](https://github.com/user-attachments/assets/f28988d3-971b-4628-b15d-fa97ae35415d)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/0f6659ee-03eb-444f-9c12-e27bd83c9018)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/6e9eca3e-16af-45b4-a215-cf5e553553b5)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/db16ffab-88cf-42d1-898b-514f6ea81bfa)

```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/fd80308e-13ce-42e7-bbfc-95c85b94d3a1)

```
df
```
![image](https://github.com/user-attachments/assets/55c00ce5-4807-4c4b-b5ba-693baea70c02)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/14491dfb-9b14-490d-a72a-795587a336af)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/1fd35079-fc5b-4aa2-aa4c-a4aee7bf782d)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/6043f199-4c89-4766-9bf5-8bf4cd80ff00)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/733be3d0-6b55-4c63-ace7-0b8b71c55a1c)

```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/3ddf6f07-ca2b-4c0b-be71-f5bf89a442c1)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/182cb7f1-566d-48c4-945c-d626f559ed04)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/3bc0aab3-8c6e-473e-aad3-a493c5d22ea4)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/81b67e55-de58-4328-811e-da555cf19fda)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/92fd09fc-2481-4388-9c69-a91c214ed2f8)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/096d8520-d809-4e85-8d2e-7d821b79762b)

```
numeric_df = df.select_dtypes(include=[np.number])
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```
![image](https://github.com/user-attachments/assets/67d455f8-e11b-49b0-a94a-d4e887870f3a)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/980f7eda-f022-4e82-880b-63f0c2fb77d9)


# RESULT
       perform Exploratory Data Analysis on the given data set is done.
