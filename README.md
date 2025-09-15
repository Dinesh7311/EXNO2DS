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

DONE BY : DINESH S

REG NO: 212224240038


python
import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

df=pd.read_csv('/content/titanic_dataset.csv')

df.head()
<img width="1377" height="638" alt="ds11" src="https://github.com/user-attachments/assets/146c2b57-3750-4eed-89c0-327fe56a301b" />

python
df.info()
<img width="1332" height="463" alt="ds22" src="https://github.com/user-attachments/assets/6421375f-197e-4e59-95c5-4244725976c3" />

python
df.dtypes
<img width="1547" height="862" alt="ds33" src="https://github.com/user-attachments/assets/255928de-73b5-4a74-a82d-20d06baf6f3a" />

python
df.describe()
<img width="1320" height="313" alt="ds44" src="https://github.com/user-attachments/assets/32a6bec2-9d31-4357-8930-38008f92da30" />


python
df["Age"].value_counts()


<img width="1340" height="457" alt="ds55" src="https://github.com/user-attachments/assets/cafe5a14-2eee-4009-8518-937569fbfae0" />

python
df.shape

<img width="1492" height="57" alt="ds66" src="https://github.com/user-attachments/assets/aadeec55-fc32-483b-9962-27ffd2714431" />


python
df.set_index("PassengerId",inplace=True)

df

<img width="1338" height="428" alt="ds77" src="https://github.com/user-attachments/assets/f988c3d6-f0f1-40ef-b0f4-2c0e66e4c13e" />


python
df.nunique()

<img width="1540" height="408" alt="ds88" src="https://github.com/user-attachments/assets/f944a5fe-e3a1-4dd9-a37a-58665b210ceb" />

python
sns.countplot(data=df,x="Age")

<img width="1327" height="483" alt="age" src="https://github.com/user-attachments/assets/6c5c12b8-05db-4379-9360-131994172382" />


python
df.rename(columns={'Sex':'Gender'},inplace=True)
df
<img width="1347" height="457" alt="gender" src="https://github.com/user-attachments/assets/cddb0fd6-736a-4971-88ca-0288aa349135" />

python
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

<img width="1398" height="551" alt="height" src="https://github.com/user-attachments/assets/c901eef9-5180-47a6-82d5-8b5c50124358" />


python
df.boxplot(column="Age",by="Survived")

<img width="1202" height="516" alt="survived" src="https://github.com/user-attachments/assets/074245cc-e9ea-4aee-8de7-7f6017c094be" />

python
sns.scatterplot(x=df["Age"],y=df["Fare"])


<img width="876" height="532" alt="fare" src="https://github.com/user-attachments/assets/577d069e-f63f-4575-bfcd-560ea328663e" />

python
p = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)

<img width="902" height="527" alt="pclass" src="https://github.com/user-attachments/assets/9da2a4cd-5171-432d-b1a3-ad25f4654c5b" />

python
sns.catplot(data=df,col="Survived",hue="Gender",y="Age",x="Pclass",kind="box")

<img width="1415" height="627" alt="hue" src="https://github.com/user-attachments/assets/8f053d4d-1077-4bf1-9057-92f5aa663649" />

python
corr = df.corr(numeric_only=True)
sns.heatmap(corr, annot=True)

<img width="1110" height="532" alt="heatmap" src="https://github.com/user-attachments/assets/284f6b8c-4230-4bec-9ced-efc9c9867e67" />

# RESULT
Hence performing Exploratory Data Analysis on the given data set is successfully executed.
