# Exno:1
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
![1](https://github.com/user-attachments/assets/8889c9f9-159e-4e57-8381-6c203d322b66)

```
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
print(df.info)
```
![2](https://github.com/user-attachments/assets/e2b73ff7-a7a8-49b5-aea3-53e897222e38)

```
import pandas as pd
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
print(df.head(13))
```
![3](https://github.com/user-attachments/assets/f314378d-61e5-448a-99e2-cc1ec87b160a)

```
import pandas as pd
print(df.tail(12))
```
![4](https://github.com/user-attachments/assets/963587fd-7594-4d83-a1cb-99aa5dc97878)

```
import pandas as pd
print(df.describe)
```
![5](https://github.com/user-attachments/assets/63010216-7dea-47cd-b448-167761558870)

```
df.isnull().sum()
```
![6](https://github.com/user-attachments/assets/62f92261-76b7-47a6-aa36-cf3b653c9695)

```
df.nunique()
```
![7](https://github.com/user-attachments/assets/09310bee-f3c4-4d4f-9d29-f447fe260904)

```
mn = 0  
df.TOTAL.fillna(mn, inplace=True)
df
```
![8](https://github.com/user-attachments/assets/82a58d07-1188-48f9-84c4-26eb70677b11)

```
min=df.M4.min()
min
```
![9](https://github.com/user-attachments/assets/efdb09ac-e92c-430f-938e-5229b8c11178)

```
df.M4.fillna(min,inplace=True)
df
```
![10](https://github.com/user-attachments/assets/3ad98fb6-d56c-4aae-891a-81bbd63c8ba0)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![11](https://github.com/user-attachments/assets/9f2afb93-54cf-4cff-bdd1-3d62837a5d06)

```
sns.boxplot(data=af)
```
![12](https://github.com/user-attachments/assets/91fffb91-78ef-4d9e-9499-325a3f5514bd)

```
sns.scatterplot(data=af)
```
![13](https://github.com/user-attachments/assets/9229a890-ab16-4560-b1d8-755e0722912c)

```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![14](https://github.com/user-attachments/assets/64e985e6-3450-41c1-a6b8-d7bc5623c9dd)

```
af=af[((af>=low)&(af<=high))]
af
```
![15](https://github.com/user-attachments/assets/ec2395f3-6e0c-4b02-a4b2-5cf4879fc1c1)

```
af.dropna()
```
![16](https://github.com/user-attachments/assets/8995d885-e20d-48ce-af7c-a7e6fadb0bdf)

```
sns.boxplot(data=af)
```
![new s 1](https://github.com/user-attachments/assets/1769dd85-7a75-4154-9499-27bd136e3034)

```
sns.scatterplot(data=af)
```
![new s 2](https://github.com/user-attachments/assets/ecfcfa84-43c8-41ba-8f52-315576252e1a)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![17](https://github.com/user-attachments/assets/afb7c731-7451-4c9b-a520-4a53e9762d74)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![18](https://github.com/user-attachments/assets/79e34650-6a0f-416f-9ad9-ea77058ca668)


# Result
Thus the program executed sucessfully.
