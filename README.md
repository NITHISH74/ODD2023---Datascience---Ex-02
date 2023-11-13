# Ex-02-Outlier:
### Date:
## Aim:
To read the given csv data and perform data for Outlier Detection and Removal.
## Algorithm:
### Step 01:
Remove outliers using IQR
### Step 02:
After removing outliers in step 1, you get a new dataframe.
### Step 03:
Use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result
### Step 04:
For the data set height_weight.csv find the following
### Step 05:
Using IQR detect weight outliers and print them.
### Step 06:
Using IQR, detect height outliers and print them

## Program:
```python
import pandas as pd
import numpy as np
import seaborn as sns
import pandas as pd
from scipy import stats

df = pd.read_csv("/content/heights.csv")

sns.boxplot(data=df)
sns.scatterplot(data=df)

max =df['height'].quantile(0.90)
min =df['height'].quantile(0.15)

max
min

dq = df[((df['height']>=min)&(df['height']<=max))]
dq

low = min-1.5*iqr
high = max+1.5*iqr

dq = df[((df['height']>=min)&(df['height']<=max))]
dq
```
## ZScore:
```python
import pandas as pd
import numpy as np
import seaborn as sns
import pandas as pd
from scipy import stats

data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}

df = pd.DataFrame(data)
df

sns.boxplot(data=df)
z = np.abs(stats.zscore(df))

print(df[z['weight']>3])

val = [12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]

out=[]

def d_o(val):
ts=3
m=np.mean(val)
sd=np.std(val)
for i in val:
z=(i-m)/sd
if np.abs(z)>ts:
  out.append(i)
return out

op = d_o(val)
op
```
## Output:
![image](https://github.com/NITHISH74/ODD2023---Datascience---Ex-02/assets/94164665/3f50d2aa-eebe-4b7a-b72f-66ea7860d4d4)


![image](https://github.com/NITHISH74/ODD2023---Datascience---Ex-02/assets/94164665/d292cdb5-156c-4e84-bde4-5216418cfd6d)


![image](https://github.com/NITHISH74/ODD2023---Datascience---Ex-02/assets/94164665/cbd71a72-d154-4764-b767-e716baa78195)


![image](https://github.com/NITHISH74/ODD2023---Datascience---Ex-02/assets/94164665/dd56a0a1-b8dc-4116-8499-a351358e54d6)


## Result:
Thus, the given data is read,remove outliers and save a new dataframe was created and executed successfully.
