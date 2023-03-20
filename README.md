# Ex-01_DS_Data_Cleansing

# AIM

To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation

Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# ALGORITHM

## STEP 1

Read the given Data

## STEP 2

Get the information about the data

## STEP 3

Remove the null values from the data

## STEP 4

Save the Clean data to the file

# CODE

### DATA_SET.CSV FILE

```python
import pandas as pd
import numpy as np
df = pd.read_csv("/content/Data_set.csv")
df.head(5)
df.info()
df.isnull().sum()
#MODE:
df['show_name'] = df['show_name'].fillna(df['show_name']).mode()[0]
df['aired_on'] = df['aired_on'].fillna(df['aired_on']).mode()[0]
df['original_network'] = df['original_network'].fillna(df['original_network']).mode()[0]
#MEAN:
df['rating'] = df['rating'].fillna(df['rating']).mean()
df['current_overall_rank'] = df['current_overall_rank'].fillna(df['current_overall_rank']).mean()
#FORWARD METHOD:
df['watchers'] = df['watchers'].fillna(method='ffill')
#DUPLICATES:
df.duplicated()
df.info()
df.isnull().sum()
```

### LOAN_DATA.CSV

```python
import pandas as pd
import numpy as np
df = pd.read_csv("/content/Loan_data.csv")
df.head()
df.info()
df.isnull().sum()
#MODE:
df['Gender'] = df['Gender'].fillna(df['Gender'].mode()[0])
df['Self_Employed'] = df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df['Dependents'] = df['Dependents'].fillna(df['Dependents'].mode()[0])
#MEAN:
df['LoanAmount'] = df['LoanAmount'].fillna(df['LoanAmount'].median())
#VALUE METHOD:
df['Loan_Amount_Term'] = df['Loan_Amount_Term'].fillna(value=360.0)
#BACKWARD METHOD:
df['Credit_History'] = df['Credit_History'].fillna(method='bfill')
#DUPLICATES:
df.duplicateed()
df.info()
df.isnull().sum()
```

# OUPUT

### First File

### Data_Set.csv FILE

![output](/1.png)

### INFO BEFORE CLEANING

![output](/2.png)

### Isnull.().sum() before cleaning

![output](/3.png)

### MODE

![output](/4.png)

### MEAN

![output](/5.png)

### FORWARD METHOD

![output](/6.png)

## DUPLICATES

![output](/7.png)

## INFO AFTER CLEANING

![output](/8.png)

## isnull().sum() after cleaning

![output](/9.png)

### Second File

### Loan_Data.csv FILE

![output](/a.png)

### INFO BEFORE CLEANING

![output](/b.png)

### Isnull.().sum() before cleaning

![output](/c.png)

## MODE

![output](/d.png)

### MEDIAN

![output](/e.png)

### VALUE METHOD

![output](/f.png)

### BACKWARD METHOD

![output](/g.png)

### DUPLICATES

![output](/h.png)

### INFO AFTER CLEANING

![output](/i.png)

### isnull().sum() after cleaning

![output](/j.png)

### RESULT:
Thus the given data is read,cleansed and cleaned data is saved into the file.
