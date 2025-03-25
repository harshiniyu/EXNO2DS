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
## Name: Harshini Y
## Reg no:212223240050
## CODING AND OUTPUT
 ```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2025-03-25 111721](https://github.com/user-attachments/assets/86e2fd54-ba53-488e-82a9-f3a07f9b62a9)
```
df.info()
```
![Screenshot 2025-03-25 111840](https://github.com/user-attachments/assets/3cb658d9-ebe5-4d10-9b9f-3491a15c5c72)
```
df.shape
```
![Screenshot 2025-03-25 111941](https://github.com/user-attachments/assets/45fbe227-1eec-4be3-b0c2-e3a5102d6da6)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2025-03-25 112018](https://github.com/user-attachments/assets/8467c1af-16c9-4521-a34d-72e1bbe2bc34)
```
df.nunique()
```
![Screenshot 2025-03-25 112052](https://github.com/user-attachments/assets/55685065-cf4a-4ed4-bccf-a9b4eac3ba27)
```
df["Survived"].value_counts()
```
![Screenshot 2025-03-25 112123](https://github.com/user-attachments/assets/41805ac4-ddb4-40dc-b84e-546f05a5c28c)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```    
![Screenshot 2025-03-25 112157](https://github.com/user-attachments/assets/3270cef0-2b26-4e41-aeee-d4e6a8b66ea6)

```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-25 112321](https://github.com/user-attachments/assets/83cbb144-c7ad-45c7-908b-ab3a5dc301f3)
```
df
```
![Screenshot 2025-03-25 112401](https://github.com/user-attachments/assets/7f07e56d-f1e3-40af-b6e5-e617aad4fad4)

```
df.Pclass.unique()
```
![Screenshot 2025-03-25 112408](https://github.com/user-attachments/assets/89f8848f-08d1-41c4-a133-ce70a2626b30)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-25 112420](https://github.com/user-attachments/assets/341ef0f3-72ec-4909-ac6a-3f8b6b70e49a)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-25 112429](https://github.com/user-attachments/assets/7b8e4f3b-ba65-4fc7-a2ee-1719d3f3034b)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-25 112751](https://github.com/user-attachments/assets/5d7bb5e6-e824-4503-a9bb-919918b845ee)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2025-03-25 112928](https://github.com/user-attachments/assets/446f20e8-7476-4bea-ba30-bbe335db3e26)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-25 112937](https://github.com/user-attachments/assets/876d67aa-146c-42d1-8f1b-2e2540871ed7)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2025-03-25 112946](https://github.com/user-attachments/assets/836fa253-4119-4e58-b5e7-02790b8b0053)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![Screenshot 2025-03-25 112955](https://github.com/user-attachments/assets/6e05056e-8a4d-4bc1-bdfc-b98d71cc427d)

```
# Select only numeric features for correlation calculation
numeric_df = df.select_dtypes(include=np.number)

# Calculate the correlation matrix
corr = numeric_df.corr()

# Generate the heatmap
sns.heatmap(corr, annot=True)
```

![Screenshot 2025-03-25 113001](https://github.com/user-attachments/assets/32bb0d9c-6892-4d70-8555-41fb73b7be0e)

```
sns.pairplot(df)
```

![Screenshot 2025-03-25 113024](https://github.com/user-attachments/assets/cb608e7f-67eb-44ea-ae18-6854503be955)

# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
