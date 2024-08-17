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
df=pd.read_csv("SAMPLEIDS.csv")
df
```     
![image](https://github.com/user-attachments/assets/30d6f69e-89d8-4b96-b3da-a97d3ed0bad3)
``` 
df.isnull().sum()

``` 
![image](https://github.com/user-attachments/assets/a6021fd0-fa2e-477d-9286-c93d723637d3)
``` 
df.isnull().any()
``` 
![image](https://github.com/user-attachments/assets/2228cafe-dd89-44b0-8a85-96e62605f2b0)
``` 
df.fillna(0)
``` 
![image](https://github.com/user-attachments/assets/56537fd9-9eea-4986-a163-f98f084a2a26)
``` 
df.fillna(method = 'ffill')
``` 
![image](https://github.com/user-attachments/assets/88d5faa3-3ae1-4f04-bfbc-dd4bdbcb88ba)
``` 
df.fillna(method = 'bfill')
``` 
![image](https://github.com/user-attachments/assets/103ab318-eac8-47e3-b29c-44fbe1e2d05d)
``` 
df_dropped = df.dropna()
df_dropped
``` 
![image](https://github.com/user-attachments/assets/811c9b60-6936-4ef0-80ee-3700c590ff96)
``` 
import pandas as pd
import  seaborn as  sns
ir=pd.read_csv('iris.csv')
ir
``` 
![image](https://github.com/user-attachments/assets/5c96dac0-cbfe-4c57-a54a-e69cb2f89cd0)
``` 
ir.describe()
``` 
![image](https://github.com/user-attachments/assets/71459990-8e9e-483b-8aea-b5c83b9c1c99)
``` 
sns.boxplot(x='sepal_width',data=ir)
``` 
![image](https://github.com/user-attachments/assets/e2347a2c-6fa5-4eaa-9d04-17820a1eef3c)
``` 
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
``` 
![image](https://github.com/user-attachments/assets/3b947f82-9c35-4944-8904-af3e15f8ee3f)
``` 
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
``` 
![image](https://github.com/user-attachments/assets/e918061f-8fc1-4696-8d36-27677e7b82b3)

![image](https://github.com/user-attachments/assets/314fe55e-5905-4f56-8ccc-679f0c6a4128)
``` 
sns.boxplot(x='sepal_width',data=delid)
``` 
![image](https://github.com/user-attachments/assets/9f21e90f-292d-4f9f-a995-bd2d1c808ef1)
``` 
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset
``` 

![image](https://github.com/user-attachments/assets/02a6cfb6-073a-4f5c-8204-80124ce305a3)

















# Result

 Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
