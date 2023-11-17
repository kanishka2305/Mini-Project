# Mini-Project
# Date:
# Aim:
To implement data science techniques in weight-height dataset
# Methodologies:
##1.Importing Libraries
2.Loading Data
3.Performing Simple EDA
4.Feature Engineering & Selection
5.Model Visulization
# Code:
```py
Developed by:Kanishka.V.S
REgister no:212222230061
```
```py
import numpy as np
import pandas as pd
import io
from scipy import stats

from google.colab import files
uploaded = files.upload()

df = pd.read_csv(io.BytesIO(uploaded['weight-height.csv']))
print(df)

df.head()
df.isnull().sum()
df.drop("Gender",axis=1,inplace=True)
df.head()
df1=df.copy()
df.boxplot()
df.shape

z=np.abs(stats.zscore(df))
z

df1=df1[(z<3).all(axis=1)]
df1

df2=df.copy()
df2.head()
q1=df2.quantile(0.25)
q3=df2.quantile(0.75)
q1
q3
iqr=q3-q1
iqr
df2_new=df2[((df2>=(q1-1.5*iqr))&(df2<=(q3+1.5*iqr))).all(axis=1)]
df2_new.shape
df2_new.boxplot()
df2
```
# Output:
![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/f08e8f40-cfd5-4182-977d-5de133caf5fa)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/4b8abc06-fb01-4fae-9dac-4be1b7bc1019)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/a682701a-eb0a-4078-b164-b3d40a802870)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/22185243-e77f-4aba-8e1b-d02752943fba)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/f11940e7-199f-4974-8001-66a7cc02d62d)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/66d61400-dd22-402a-94d5-bdd1dcf7383f)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/56413a24-508b-419c-9837-e40b8f9afe07)

![image](https://github.com/kanishka2305/Mini-Project/assets/113497357/93527682-e826-4450-b4d1-20718333d1d8)
# Result:
Thus above program is required for weight-height was analyzed successfully
