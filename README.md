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
~~~
import pandas as pd
df = pd.read_csv('/content/titanic_dataset.csv')
df
~~~
![image](https://github.com/user-attachments/assets/fb587ce3-f65e-40e7-bca2-9df75f22a377)
~~~
df.dropna(inplace=True)
df.isna().sum()
~~~
![image](https://github.com/user-attachments/assets/a2326e2f-ac80-4cf0-bc9b-05445d89f22b)
~~~
df.info()
~~~
![image](https://github.com/user-attachments/assets/009f3be1-8565-4685-94a1-0f60735ad126)
~~~
df.shape
~~~
![image](https://github.com/user-attachments/assets/31f487f4-ea10-4337-8b14-8e3efa6e2184)
~~~
df.set_index('PassengerId', inplace=True)
df.describe()
~~~
![image](https://github.com/user-attachments/assets/e96a0c21-0cc0-4996-9eab-ed182452c72e)
~~~
df
~~~
![image](https://github.com/user-attachments/assets/becd6e7a-cdc0-475a-99a1-ee075acbba2e)
~~~
df.nunique()
~~~
![image](https://github.com/user-attachments/assets/25e59ec6-1075-4b28-9cab-7f4d6feba34e)
~~~
df["Survived"].value_counts()
~~~
![image](https://github.com/user-attachments/assets/54a18554-0379-44de-9251-0ad3a26aeb0d)
~~~
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
~~~
![image](https://github.com/user-attachments/assets/6cd94b75-7834-4937-8815-1773b0929c4f)
~~~
import seaborn as sns
sns.countplot(data=df, x="Survived")
~~~
![image](https://github.com/user-attachments/assets/b8924350-5a63-41c7-b46f-46c55022b213)
~~~
df
~~~
![image](https://github.com/user-attachments/assets/0943ef82-41dd-493c-b061-0655a4ca32dd)
~~~
df.Pclass.unique()
~~~
![image](https://github.com/user-attachments/assets/7d3657a6-db5f-40c7-97fb-adda0dfa4dcd)
~~~
df.rename(columns={'Sex':'Gender'},inplace=True)
df
~~~
![image](https://github.com/user-attachments/assets/d1e75cf2-3859-4c3a-a9ea-80a18d573bef)
~~~
sns.catplot(x='Gender',col='Survived',kind="count",data=df,height=5,aspect=.7)
~~~
![image](https://github.com/user-attachments/assets/110f87c9-15e9-4aa5-b8bf-72ebc865e51a)
~~~
sns. catplot(x='Survived', hue="Gender", data=df, kind = "count" )
~~~
![image](https://github.com/user-attachments/assets/9e3dcd1e-98ae-42a8-84af-9a733eb2872b)
~~~
sns. catplot(data=df, col = "Survived", x = "Gender", hue="Pclass", kind = "count")
~~~
![image](https://github.com/user-attachments/assets/f56e1271-adcc-41be-b6c7-5fcf2dfd8e46)
~~~
df_numeric = df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
~~~
![image](https://github.com/user-attachments/assets/1d24cffa-c5a3-4e4d-9548-e98b52d7f096)
~~~
sns.pairplot(df)
~~~
![image](https://github.com/user-attachments/assets/b948cf89-28d1-46b0-bac4-bde963e5695d)


# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
