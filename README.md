# Ex02-Outlier
You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

## ALGORITHM:
### STEP 1:
Read the given data
### STEP 2:
Get the information about the data.
### STEP 3:
Detect the Outliers using IQR method and Z score.
### STEP 4:
Remove the outliers:
### STEP 5:
Plot the datas using box plot.

## PROGRAM:
Name: BALACHANDRAN S

Register No: 212222100008

```
import pandas as pd
import seaborn as sns
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![Screenshot 2023-09-12 105133](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/d995dfaf-09c8-4bfb-b7ab-eed669dda5d4)
```
sns.boxplot(data=af)
```
![Screenshot 2023-09-12 105350](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/ce554fb2-9814-4ab0-a2fb-ebd2d56a74e1)
```
sns.scatterplot(data=af)
```
![Screenshot 2023-09-12 105807](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/de3336a5-59b0-4855-a44c-394905409355)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
irq=af.quantile(0.5)
```

```
low=q1-1.5*iqr
low
```

![Screenshot 2023-09-12 110203](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/f2830e1c-4bd6-4305-bf96-0413fb62b3ff)

```
high=q3+1.5*iqr
high
```

![Screenshot 2023-09-12 110343](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/bff9a9ba-161d-4d29-9318-f25155144ea8)

```
aq=af[((af>=low)&(af<=high))]
aq.dropna()
```

![Screenshot 2023-09-12 110431](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/bf7f5338-61b4-4fea-8abe-fdfd5b77d3d1)

```
sns.boxplot(data=af)
```

![Screenshot 2023-09-12 110542](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/ea69196c-4fca-4c95-84a9-449ab0a175f4)

```
af=af[((af>=low)&(af<=high))]
af.dropna()
```

![Screenshot 2023-09-12 110830](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/336d9592-c6c7-45ce-ad1d-3266b50918ab)

```
sns.boxplot(data=af)
```

![Screenshot 2023-09-12 111000](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/1a926606-850d-4c2b-be3d-9bc669fb364f)

```
sns.scatterplot(data=af)
```

![Screenshot 2023-09-12 111228](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/8c6ae896-183d-434f-8702-8dc686e2fb42)

```
import pandas as pd
import numpy as np
import seaborn as sns
import pandas as pd
from scipy import stats
```

```
data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,2
df=pd.DataFrame(data)
df
```

![Screenshot 2023-09-12 111405](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/dc46dbcc-15e3-4ef3-bfd2-f3c70f094ab7)

```
sns.boxplot(data=df)
```

![Screenshot 2023-09-12 111523](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/91d675db-92f1-4688-8471-9f6553474769)

```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```

![Screenshot 2023-09-12 111619](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/ec78b6c7-94d9-4223-9e63-522b88e7965d)

```
val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
df=pd.DataFrame(data)

```
```
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
```

```
op=d_o(val)
op
``
<img width="68" alt="image" src="https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/121222763/80263fed-d9b8-4069-93d2-d194f424a419">

```python
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
```

```
id=pd.read_csv("iris.csv")
id
```

![Screenshot 2023-09-12 112346](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/b6ac583f-4ef7-4c0c-9708-d232893af990)

```
sns.boxplot(x='sepal_width',data=id)
```

![Screenshot 2023-09-12 112455](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/3fdff14a-b9c2-49ff-b282-cf3a7dc886e0)

```
c1=id.sepal_width.quantile(0.25)
c3=id.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
```
rid=id[((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```

![Screenshot 2023-09-12 112554](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/e0617da4-18d5-4f10-a988-144fa7368e0d)

```
rid=id[((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```

![Screenshot 2023-09-12 112639](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/307769f2-5a1f-4ce4-859f-b7aca6b448b0)

```
delid=id[~((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
delid
```

![Screenshot 2023-09-12 112727](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/026c8a3e-33ec-4901-92e3-8fd795d76b7e)

```
sns.boxplot(x='sepal_width',data=delid)
```

![Screenshot 2023-09-12 112833](https://github.com/Balachandran143/ODD2023---Datascience---Ex-02/assets/118886489/be61b8a7-cb57-45f8-b520-1ba374bd59d8)

## Result:
Hence the given set of data is read and the outliers are removed using the IQR method and Zscore method.
