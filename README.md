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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2024-09-04 190356](https://github.com/user-attachments/assets/3af2844b-7421-494b-8ea0-276835d01b9c)
```
df.isnull().sum()
```
![Screenshot 2024-09-04 190445](https://github.com/user-attachments/assets/b3f22708-0637-49a1-a348-b279d5bb4b82)
```
df.dropna(inplace=True)
df
```
![Screenshot 2024-09-04 190514](https://github.com/user-attachments/assets/cb8a8784-7e54-4354-92e2-5b2d17bd2ed6)
```
df.info()
```
![Screenshot 2024-09-04 190544](https://github.com/user-attachments/assets/420b5b82-0390-4cc6-9a13-83d6613cb3bf)
```
df.shape
```
![Screenshot 2024-09-04 190625](https://github.com/user-attachments/assets/0c57b7ce-49e7-4dfd-9f2b-3fe0221029e6)
```
df.set_index("PassengerId",inplace=True)
df
```
![Screenshot 2024-09-04 190656](https://github.com/user-attachments/assets/8528e91d-c153-44f0-9882-3dc017a94a71)
```
df.nunique()
```
![Screenshot 2024-09-04 190744](https://github.com/user-attachments/assets/e6996f62-5ed5-4492-b99f-98f3d96b8439)
```
df["Survived"].value_counts()
```
![Screenshot 2024-09-04 190922](https://github.com/user-attachments/assets/3bf33e28-ccee-4c79-96dd-f592b4ada952)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2024-09-04 190958](https://github.com/user-attachments/assets/1723e5b9-8ea9-4fff-b72f-324073290251)
```
import matplotlib.pyplot as plt
import seaborn as sns
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-09-04 191039](https://github.com/user-attachments/assets/b7ab390f-6ece-4b61-99ae-4f960bcf5fba)
```
df.Pclass.unique()
```
![Screenshot 2024-09-04 191130](https://github.com/user-attachments/assets/c62131a6-8dc7-422d-9698-dde90bb772fc)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2024-09-04 191143](https://github.com/user-attachments/assets/3dba5f26-4d03-4390-93e7-ac2fb21d8b23)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-09-04 191308](https://github.com/user-attachments/assets/a9f893e5-bcd5-4ae1-a469-570cb216f3b7)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2024-09-04 191354](https://github.com/user-attachments/assets/9c29b991-e207-49f9-89fb-cc088ffdf6af)
```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-09-04 191429](https://github.com/user-attachments/assets/9090ff81-c952-46ec-8a9f-c16d563620cd)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-09-04 191503](https://github.com/user-attachments/assets/349a6edd-fb3a-4d2d-a888-b64e27cb0877)

# RESULT
Hence performing Exploratory Data Analysis on the given data set is successful
