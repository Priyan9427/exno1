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
df = pd.read_csv('SAMPLEIDS.csv')
df
```
<img width="1043" height="866" alt="Screenshot 2025-09-06 091546" src="https://github.com/user-attachments/assets/fc55cfa3-abf1-4f8b-9637-581b17e14b05" />

```
df.head()
```
<img width="1010" height="278" alt="Screenshot 2025-09-06 091720" src="https://github.com/user-attachments/assets/73d7dbb2-a1c3-44ab-9379-4718b986e943" />
```
df.tail()
```
<img width="1052" height="250" alt="Screenshot 2025-09-06 091815" src="https://github.com/user-attachments/assets/9a15d187-a070-4d81-b73a-a54e35558a82" />


```
df.isnull()
```


<img width="818" height="862" alt="Screenshot 2025-09-06 092020" src="https://github.com/user-attachments/assets/57a92db1-f3b3-46fc-93b2-e29789fd89ef" />

```
df.isnull().sum()
```
<img width="203" height="566" alt="Screenshot 2025-09-06 092126" src="https://github.com/user-attachments/assets/49d4fc5a-44c3-4d5e-ba4b-f39ab8a78e14" />

```
df.isnull().any()
```
<img width="228" height="543" alt="Screenshot 2025-09-06 092207" src="https://github.com/user-attachments/assets/f399f4d0-0d34-43b7-8c2f-cfaae995a426" />

```
df.dropna()
```
<img width="1038" height="592" alt="Screenshot 2025-09-06 093446" src="https://github.com/user-attachments/assets/1fd291b9-a851-4276-8239-661fcac1c6b1" />


```
df.dropna(axis=1)
```
<img width="389" height="881" alt="Screenshot 2025-09-06 093502" src="https://github.com/user-attachments/assets/c5420dfe-4119-4b6a-b4a3-15cd7fd7807d" />


```
df.fillna(method='ffill')
```
<img width="1096" height="915" alt="Screenshot 2025-09-06 093402" src="https://github.com/user-attachments/assets/6afb03d0-d607-41d3-b3e6-be325c0709e3" />


```
df.fillna(method='bfill')
```

<img width="1086" height="902" alt="Screenshot 2025-09-06 093348" src="https://github.com/user-attachments/assets/4850c43c-5861-447e-af1e-8c73e5ed5bd3" />

```
df.fillna({'GENDER':'MALE','NAME':'VARUN','M1':'010'})
```
<img width="1072" height="900" alt="Screenshot 2025-09-06 093222" src="https://github.com/user-attachments/assets/da66ee7a-ce9f-43a4-a202-cf878be2d202" />


```
import pandas as pd
ir=pd.read_csv('iris.csv')
ir
```
<img width="723" height="544" alt="Screenshot 2025-09-06 093155" src="https://github.com/user-attachments/assets/11f0e0c4-1b4b-41dc-9a29-f3f8fca9dee6" />

```
ir.describe()
```
<img width="626" height="408" alt="Screenshot 2025-09-06 093120" src="https://github.com/user-attachments/assets/6181cb8d-d887-445b-84dc-efea2e43ebf5" />


```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="746" height="623" alt="Screenshot 2025-09-06 093058" src="https://github.com/user-attachments/assets/689ae49d-2060-4325-958e-2b47f8529314" />


```
out=ir[(ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr))]
out['sepal_width']
```

<img width="234" height="244" alt="Screenshot 2025-09-06 093039" src="https://github.com/user-attachments/assets/a08d0a18-f786-464c-a713-5f25dfc42cbe" />

```
nrml=ir[~(ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr))]
nrml['sepal_width']
```
<img width="284" height="548" alt="Screenshot 2025-09-06 093017" src="https://github.com/user-attachments/assets/a1cca138-4cb4-4534-bac7-883b2ae707d7" />


```
import numpy as np
import scipy.stats as stats
he = pd.read_csv('heights.csv')
he
```
<img width="267" height="615" alt="Screenshot 2025-09-06 092945" src="https://github.com/user-attachments/assets/df479ee8-9843-418d-a6df-c80566255bc3" />

```
z=np.abs(stats.zscore(he['height']))
z
```
<img width="709" height="105" alt="Screenshot 2025-09-06 092924" src="https://github.com/user-attachments/assets/0b33c5c6-bc80-47c9-987f-4eae95d331d3" />


```
he1=he[z<3]
he1
```

<img width="237" height="561" alt="Screenshot 2025-09-06 092904" src="https://github.com/user-attachments/assets/35f02e29-653b-4f27-b864-412a83ad89c8" />

# Result

Thus the given data successfully performed data cleaning and saved the cleaned data to a file.


