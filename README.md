# Experiment no.1

Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
<img width="1000" height="860" alt="image" src="https://github.com/user-attachments/assets/69188feb-b10b-4629-a1df-6d343baf6258" />
```
df.shape
```
<img width="141" height="42" alt="image" src="https://github.com/user-attachments/assets/3c02cd5d-be74-4b6b-8a05-051ef5649f1c" />
```
df.describe()
```
<img width="1007" height="858" alt="image" src="https://github.com/user-attachments/assets/301b6fe6-4b21-4c42-a65b-0f138db984d3" />
```
df.info()
```
<img width="413" height="430" alt="image" src="https://github.com/user-attachments/assets/393f7948-b99d-49bc-a5f1-2ad1a87b7a23" />
```
df.head(3)
```
<img width="1007" height="145" alt="image" src="https://github.com/user-attachments/assets/8002fc8d-2d18-455d-bd99-703b6bff6770" />
```
df.tail(3)
```
<img width="1001" height="136" alt="image" src="https://github.com/user-attachments/assets/4b9df1ea-73e0-43f0-aa97-959d4fd962c2" />
```
df.isna().sum()
```
<img width="198" height="562" alt="image" src="https://github.com/user-attachments/assets/db1453f5-d2c1-411e-b605-ebd92630de1b" />
```
df.shape
```
<img width="97" height="31" alt="image" src="https://github.com/user-attachments/assets/5973a5ab-76b8-40e2-a14d-4e745ccd909f" />
```
x=df.dropna(how='any')
df
```
<img width="1011" height="848" alt="image" src="https://github.com/user-attachments/assets/eb174a00-e808-4c52-9cc0-2999be0c6f6b" />
```
x2=df.dropna(how='all').shape
df
```
<img width="1010" height="877" alt="image" src="https://github.com/user-attachments/assets/456d9fee-4e03-4369-95b4-caed7686fd11" />
```
mn=df.TOTAL.mean()
mn
```
<img width="60" height="37" alt="image" src="https://github.com/user-attachments/assets/57f4b6b0-ef97-40ea-86a7-43b87aa1dc89" />
```
df.TOTAL.fillna(mn,inplace=True)
df
```
<img width="1015" height="863" alt="image" src="https://github.com/user-attachments/assets/cab4aebb-673b-44e3-a9c4-f0d1b4ba81e1" />
```
df.isnull().sum()
```
<img width="207" height="558" alt="image" src="https://github.com/user-attachments/assets/e41ec927-4ec5-476b-a5c0-e45708195e2d" />
```
df.M1.dropna(inplace=True)
df
```
<img width="1016" height="863" alt="image" src="https://github.com/user-attachments/assets/fcb56133-aadc-4698-8411-d18b870281dd" />
```
df.M1.fillna(method='ffill',inplace=True)
df
```
<img width="1010" height="610" alt="image" src="https://github.com/user-attachments/assets/a72db20a-3a9b-4289-9cab-6b7ff0be1eca" />
```
df.isnull().sum()
```
<img width="120" height="527" alt="image" src="https://github.com/user-attachments/assets/4de64fc3-382a-4b74-9bbf-06e780c9c49d" />
```
df.M2.fillna(method='ffill',inplace=True)
df
```
<img width="1017" height="570" alt="image" src="https://github.com/user-attachments/assets/ce243dad-4d38-4593-be32-db73f90a1b6a" />
```
df.isnull().sum()
```
<img width="168" height="561" alt="image" src="https://github.com/user-attachments/assets/4fc89050-66d8-4498-9c10-840a39d28192" />
```
df.M3.fillna(method='ffill',inplace=True)
df
```
<img width="1003" height="562" alt="image" src="https://github.com/user-attachments/assets/9f029d3e-c2bd-458b-ad2b-69d5e994bb22" />
```
df.isnull().sum()
```
<img width="178" height="557" alt="image" src="https://github.com/user-attachments/assets/1a250f5d-d8a8-4e1b-a661-eaf16ec6c5fa" />
```
df.duplicated()
```
<img width="145" height="913" alt="image" src="https://github.com/user-attachments/assets/de56da5c-d7e3-4f78-9eb5-3b9c63e0e8fb" />
```
df.drop_duplicates(inplace=True)
df
```
<img width="1010" height="822" alt="image" src="https://github.com/user-attachments/assets/1609087b-432a-4b92-add5-b80c839a23b0" />
```
df['DOB']
```
<img width="197" height="850" alt="image" src="https://github.com/user-attachments/assets/3c1e4b5f-9c53-4ce4-9ffe-ef104106d6e5" />
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
<img width="675" height="622" alt="image" src="https://github.com/user-attachments/assets/6d9d3237-9caf-4321-aaf7-7fc372e01638" />
```
df.dropna(inplace=True)
df
```
<img width="1003" height="692" alt="image" src="https://github.com/user-attachments/assets/5e65eeb6-00ad-4679-80f6-8050df984d04" />
```
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
<img width="692" height="628" alt="image" src="https://github.com/user-attachments/assets/0c2a5128-4ea2-4bae-a80c-e128c29cd0bb" />

OUTLIER DETECTION AND REMOVAL USING IQR
```
import pandas as pd
import seaborn as sns
import numpy as np

age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
<img width="120" height="581" alt="image" src="https://github.com/user-attachments/assets/06997ab6-8d15-49e7-bd27-c6eaffc974c2" />
```
sns.boxplot(data=af)
```
<img width="716" height="557" alt="image" src="https://github.com/user-attachments/assets/934e4371-905b-4ad1-ba59-dc36db4be5b1" />
```
sns.scatterplot(data=af)
```
<img width="691" height="545" alt="image" src="https://github.com/user-attachments/assets/72fa38a0-bf7b-43b5-92e4-8f40193e9713" />
```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
<img width="148" height="135" alt="image" src="https://github.com/user-attachments/assets/c3d7298f-5461-49cb-b34b-7f9226abcd8b" />
```
Q1=np.percentile(af,25)
Q3=np.percentile(af,75)
IQR=Q3-Q1
IQR
```
<img width="72" height="41" alt="image" src="https://github.com/user-attachments/assets/64284d3f-6ffb-4d87-8329-cef61f243d30" />
```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
lower_bound
upper_bound
```
<img width="53" height="27" alt="image" src="https://github.com/user-attachments/assets/5ad227f0-485d-4c92-a373-e33ab1782d43" />
```
outliers = [x for x in age if x < lower_bound or x > upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower bound:",lower_bound)
print("Upper bound:",upper_bound)
print("Outliers:",outliers)
```
<img width="245" height="146" alt="image" src="https://github.com/user-attachments/assets/0b706593-87b4-4d4b-9f0d-384833961ec3" />
```
af=af[((af>=lower_bound)&(af<=upper_bound))]
af
```
<img width="130" height="592" alt="image" src="https://github.com/user-attachments/assets/dd742e1e-c9bc-47e6-8ca2-ce4b9fb81282" />
```
af.dropna()
```
<img width="143" height="417" alt="image" src="https://github.com/user-attachments/assets/fa8e8438-38b6-43ad-b4b6-a56fdd2eb94c" />
```
data=[1,2,2,2,3,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print("mean of the dataset is",mean)
print("std.deviation is",std)
```
<img width="425" height="43" alt="image" src="https://github.com/user-attachments/assets/35bc0931-dc43-427a-a17c-4e10d98af9a9" />
```
threshold=3
outlier=[]
for i in data:
  z=(i-mean)/std
  if z > threshold:
    outlier.append(i)
print("outlier in dataset is",outlier)
```
<img width="257" height="37" alt="image" src="https://github.com/user-attachments/assets/78f75c9b-2d77-49e8-88e9-d0103029190b" />
```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
<img width="103" height="537" alt="image" src="https://github.com/user-attachments/assets/0a0aa79d-fa3e-4e05-88e2-6d7cbcbea341" />
```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```
<img width="117" height="62" alt="image" src="https://github.com/user-attachments/assets/fc7841bf-81ed-4830-a3d4-f5d23f2187f1" />

# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score meth
