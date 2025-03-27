# EXNO2DS-EXPLORATORY DATA ANALYSIS
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
### DEVELOPED BY : HAREESH R
### REGISTER NO:   212223230068
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('/content/titanic_dataset.csv')
df
```
![Screenshot 2025-03-27 112326](https://github.com/user-attachments/assets/5629d780-9048-4f4f-91af-86cba00face2)
```
df.info()
```
![Screenshot 2025-03-27 112407](https://github.com/user-attachments/assets/b3a1fea1-94e4-4099-8328-1f004139827e)
```
df.shape
```
![Screenshot 2025-03-27 112438](https://github.com/user-attachments/assets/b64784e3-fc88-4537-9b86-beae0cd748fd)
```
df.set_index('PassengerId',inplace=True)
df.describe()
```
![Screenshot 2025-03-27 112520](https://github.com/user-attachments/assets/cb0c8552-6a65-4054-a687-0fbf1b9b4af3)

```
df.shape

```
![Screenshot 2025-03-27 112545](https://github.com/user-attachments/assets/b8a4a18c-82ee-4b34-8204-60b3455a1309)
```
df.nunique()
```
![Screenshot 2025-03-27 112642](https://github.com/user-attachments/assets/62d66904-40b7-4266-8bd5-3937cd251b4e)

```
df["Survived"].value_counts()
```
![Screenshot 2025-03-27 112712](https://github.com/user-attachments/assets/f350099b-6dea-451b-bf0d-5117414a54ef)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-27 112744](https://github.com/user-attachments/assets/b86e3e1d-60b5-4199-8970-5b54ceb79c9a)
```
sns.countplot(data=df,x='Survived')
```
![Screenshot 2025-03-27 112839](https://github.com/user-attachments/assets/74b69eca-0f4b-4faf-8bfd-89c196bbed3e)
```
df
```
![Screenshot 2025-03-27 112909](https://github.com/user-attachments/assets/b848876c-6e08-42c7-b4ee-a8528af81c18)

```
df.Pclass.unique()
```
![Screenshot 2025-03-27 112941](https://github.com/user-attachments/assets/0282fa6c-b0e8-487e-970a-77e0235e0c82)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df

```
![Screenshot 2025-03-27 113016](https://github.com/user-attachments/assets/c3ff1f18-d7ae-4081-afdb-db1bf018460a)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-27 113054](https://github.com/user-attachments/assets/2d01fefe-184d-43f4-a156-5a9538fe90cf)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-27 113127](https://github.com/user-attachments/assets/9ac5183c-a379-4b18-93b3-2e32fcf8a971)
```
df.boxplot(column="Age",by="Survived")

```
![Screenshot 2025-03-27 113218](https://github.com/user-attachments/assets/5624471b-1772-478e-83bd-0319fca0d07e)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2025-03-27 113254](https://github.com/user-attachments/assets/02c87179-b0fe-4cca-a39f-5db1c25b0d81)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-27 113324](https://github.com/user-attachments/assets/e5bb99fd-1b5f-48a7-be80-b4c82b385ebd)
```
fig, ax1 = plt.subplots(figsize=(8,5))

plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![Screenshot 2025-03-27 113409](https://github.com/user-attachments/assets/3d5321e7-1828-498e-b207-b7f1c3505990)
```
sns.catplot(data=df,col="Survived",x="Sex",hue="Pclass",kind="count")
```
![Screenshot 2025-03-27 113439](https://github.com/user-attachments/assets/8254fe57-05a6-4972-97d7-01a6d60fba00)
```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()

sns.heatmap(corr, annot=True)
```
![Screenshot 2025-03-27 113519](https://github.com/user-attachments/assets/3c0e751c-43fc-48f6-867f-0ec5569c61a6)
```
sns.pairplot(df)
```
![Screenshot 2025-03-27 113823](https://github.com/user-attachments/assets/b78023c1-8647-4e83-ba2a-0ce2e5e895f9)
# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
