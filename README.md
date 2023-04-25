
# Workshop 3 Feature Generation

## Aim :
To perform Feature Generation techniques in the given data set
## Program Code :
import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

df=pd.read_excel("/content/Workshop_feature Engg.csv.xlsx")

df1 = df.copy()

df1.head()

df1.info()

df1.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df1['fueltype'] = le.fit_transform(df1['fueltype'])

sns.set(style ="darkgrid")

sns.countplot(df1['fueltype'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

df2 = df.copy()

enc = enc.fit_transform(df2[['CarName']]).toarray()

encoded_colm = pd.DataFrame(enc)

df2 = pd.concat([df2, encoded_colm], axis=1)

df2 = df.drop(['CarName'], axis=1)

df2.head(10)

df3 = df.copy()

df3 = pd.get_dummies(df3, prefix=['aspiration'], columns=['aspiration'])

df3.head(5)

df4 = df.copy()

df4 = pd.get_dummies(df4, prefix=['doornumber'], columns=['doornumber'])

df4.head()

df5 = df.copy()

df5 = pd.get_dummies(df5, prefix=['carbody'], columns=['carbody'])df5.head()

df6 = df.copy()

df6 = pd.get_dummies(df6, prefix=['drivewheel'], columns=['drivewheel'])

df6.head()

df7 = df.copy()

df7 = pd.get_dummies(df7, prefix=['enginelocation'], columns=['enginelocation']) df7.head()

df8 = df.copy()

df8 = pd.get_dummies(df8, prefix=['enginetype'], columns=['enginetype'])

df8.head()

df9 = df.copy()

df9 = pd.get_dummies(df9, prefix=['cylindernumber'], columns=['cylindernumber'])

df9.head()

## Ouput :

![image](https://user-images.githubusercontent.com/95179990/233083844-623e37fd-5d6f-4cbb-b2ef-ec29c29d47e5.png)
![image](https://user-images.githubusercontent.com/95179990/233085430-86456dca-b899-42a1-9117-93438ce964bc.png)
![image](https://user-images.githubusercontent.com/95179990/233085577-ebc810ee-4e7c-4982-8042-27a006c5b8e8.png)
![image](https://user-images.githubusercontent.com/95179990/233085803-6fa156e6-00bf-44df-9fd9-c6df2e9821ba.png)
![image](https://user-images.githubusercontent.com/95179990/233086000-0381d857-2b45-435b-b35a-284dd833b239.png)
![image](https://user-images.githubusercontent.com/95179990/233086119-3af12c1a-a7e5-4f4c-bdd7-8f6af6323112.png)





