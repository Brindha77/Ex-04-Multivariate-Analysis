# Ex-04-Multivariate-Analysis
## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
## STEP 1:
Import the built libraries required to perform EDA and outlier removal.

## STEP 2:
Read the given csv file.

## STEP 3:
Convert the file into a dataframe and get information of the data.

## STEP 4:
Return the objects containing counts of unique values using (value_counts()).

## STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr() .

## STEP 8:
Save the final data set into the file.

## Program:
```python
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
## OUTPUT:
## DATASET:
![Screenshot_20230411_031258](https://user-images.githubusercontent.com/118889143/231128244-74a69c50-c856-48eb-b18a-70effd79d4db.png)

## HEAD():
![Screenshot_20230411_031309](https://user-images.githubusercontent.com/118889143/231128421-117efe17-0bce-46c6-89ff-59e19297823f.png)

## INFO():
![Screenshot_20230411_031321](https://user-images.githubusercontent.com/118889143/231128816-7bc0f07d-f999-41fb-88dd-519bbb4b754b.png)

## DESCRIBE():
![Screenshot_20230411_031329](https://user-images.githubusercontent.com/118889143/231128997-e2aa5c2a-de18-4e26-882b-b8b94b7fe2f9.png)

## DATATYPE():
![Screenshot_20230411_031337](https://user-images.githubusercontent.com/118889143/231130147-9cc793d4-1feb-4f25-b379-a6fdb9d093c3.png)


## ISNULL():
![Screenshot_20230411_031346](https://user-images.githubusercontent.com/118889143/231130213-6fe0462d-fee4-4ace-9806-89ae1dde18da.png)


## Postal code has outliers:
![Screenshot_20230411_031355](https://user-images.githubusercontent.com/118889143/231130272-2be42a42-1604-49f8-9b70-baeff4420071.png)


## After removing outliers from Postal Code:
## MULTIVARIATE ANALYSIS:
## SCATTER PLOT:
![Screenshot_20230411_031406](https://user-images.githubusercontent.com/118889143/231130371-6e5e9ca2-13c1-4080-b218-a0f21ad00ed0.png)


## BARPLOT:
![Screenshot_20230411_031415](https://user-images.githubusercontent.com/118889143/231130439-7a9fb2ec-b083-40be-8565-dcbfe125c770.png)
![Screenshot_20230411_031427](https://user-images.githubusercontent.com/118889143/231130495-9aba0eca-d867-4b5c-88a3-3a2f2f3c9c2a.png)

## SEGMENTATION:
![Screenshot_20230411_031437](https://user-images.githubusercontent.com/118889143/231130580-b09b885e-2578-43dc-af66-c52f78688272.png)


## CORRESSION:
![Screenshot_20230411_031445](https://user-images.githubusercontent.com/118889143/231130738-d17bcf6e-8112-41cb-a53c-30ea9f05cd39.png)


## HEATMAP():
![Screenshot_20230411_031452](https://user-images.githubusercontent.com/118889143/231130825-b9873dac-fb42-4296-b7be-e6608f29dcdf.png)


## RESULT:
Hence The Performance of the Multivariate EDA on the given data set is verified.



