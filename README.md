# workshop-Multivariate-analysis
##AIM:
To perform Bivariate/Multivariate Analysis for the given data set.

## ALGORITHM:
1.Read the given data
2.Get information from the data
3.Perform the Multivariate Analysis
4.Save the clean data to file.

## PROGRAM:
```
DEVELOPED BY:SASIDEVI V
REGISTRATION NUMBER: 212222230136
```
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
datas=pd.read_excel(r"/content/FlightInformation.xlsx")
df=pd.DataFrame(datas)
df

df.info()
df.head()
df.isnull().sum()

#Data cleaning
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()

#NUMERICAL AND NUMERICAL
sns.scatterplot(x=df['Destination'],y=df['Price'])
sns.scatterplot(x=df['Destination'],y=df['Total_Stops'])

# NUMERICAL AND CATEGORICAL
sns.barplot(x=df["Source"],y=df["Price"],data=df)
sns.barplot(x=df['Source'],y=df['Price'],hue=df['Destination'])

DEST=df.loc[:,["Destination","Price"]]
DEST=DEST.groupby(by=["Destination"]).sum().sort_values(by="Price")
plt.figure(figsize=(7,7))
sns.barplot(x=airline.index,y="Price",data=DEST)
plt.xticks(rotation = 90)
plt.xlabel=("DESTINATION")
plt.ylabel=("PRICE")
plt.show()

sns.boxplot(x=df['Price'],y=df['Duration'])
sns.displot(df, x="Source", hue="Airline")
#MULTIVARIATE ANALYSIS 
df.corr()
sns.heatmap(df.corr(),annot=True)
```
# OUTPUT:
## DATA
![DS1](https://user-images.githubusercontent.com/118707332/229976947-c7d852de-f647-461b-9d67-09b42d90879d.png)
## df.info()
![DS2](https://user-images.githubusercontent.com/118707332/229976952-af82dc26-31d9-4501-89c8-5c73c8b0c4b9.png)
## df.head()
![DS3](https://user-images.githubusercontent.com/118707332/229976986-972ab321-7c0d-421a-b523-26225135750d.png)
## BEFORE REMOVING NULL VALUES
![DS4](https://user-images.githubusercontent.com/118707332/229976995-e871cf30-38d9-476d-b4e4-f6efc4f4b812.png)
## AFTER REMOVING NULL VALUES
![DS5](https://user-images.githubusercontent.com/118707332/229977007-a20fe47d-d596-4d0a-a8bc-08b29e5f5f90.png)
## NUMERICAL AND CATEGORICAL
![DS6](https://user-images.githubusercontent.com/118707332/229977021-99183b1e-c6f4-46a5-b47e-9f24f0dcc102.png)
![DS7](https://user-images.githubusercontent.com/118707332/229977025-6a3d15f1-af01-47a2-9970-52e8d315f0e0.png)
## NUMERICAL AND CATEGORICAL
### 1.BARPLOT:
![DS8](https://user-images.githubusercontent.com/118707332/229977032-bbc2cb57-a89c-4b6c-a4fe-d9237e31b42e.png)
![DS9](https://user-images.githubusercontent.com/118707332/229977070-09bfeefa-dfb2-4d98-a170-f5f96a175be8.png)
![DS10](https://user-images.githubusercontent.com/118707332/229977078-109cbac0-f618-4ff5-b78d-b2be4c9f1541.png)
### 2.BOXPLOT:
![DS11](https://user-images.githubusercontent.com/118707332/229977084-58c735f5-8e26-4cd8-bf64-08ea4a45f4a3.png)
### 3.DISTPLOT:
![DS12](https://user-images.githubusercontent.com/118707332/229977090-c312ce82-ae2c-4760-8e07-593a2e339a39.png)
## MULTIVARIATE ANALYSIS 
### CORRELATION
![DS13](https://user-images.githubusercontent.com/118707332/229977103-e4231bc9-cc2f-44c9-b814-ab1a57103342.png)
### HEATMAP
![DS14](https://user-images.githubusercontent.com/118707332/229977119-1d7c8635-6a54-4bd8-9851-e4d91ea0d0bc.png)


## RESULT:
Thus the Bivariate/Multivariate Analysis for the given data set is executed successfully.


