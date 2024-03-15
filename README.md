# Prediction-of-Product-Sales
## Introduction
### Project details
This Project will give an insight on the insurance charges based on conditions , 
the Conditions are age, region , sex  and smoker or non-smoker. The project will as well consider the bmi to make more accurate estimations on the charges .

# Data Imports
## Load libraries
### Mount Google drive
```
from google.colab import drive
drive.mount('/content/drive')
```

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
### Read data
```
fpath= "/content/drive/MyDrive/Course 1/Week 3/DataFolder/insurance_mod (1).csv"
insurance = pd.read_csv(fpath)
insurance.head()
```

# Data Visulaisations
## Histograms showing the distribution of the numerical variables of the insurance data

![histogram_of_insurance_data](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/f872d8e1-8eaa-4527-a875-7e07f250de61)

##  A histogram Showing the Charges
```
ax = sns.histplot(data=insurance, x='charges', bins=10, edgecolor="Black")
ax.set_title("A Histogram of the Charges")
```
![A histogram of Charges](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/4d0468dc-a0bf-4eb1-b7bc-8a56f8f25484)
### The histogram shows the count of the charges , we see that the count (10-15000) have the highest counts

##  A Histogram showing the age counts 
```
ax = sns.histplot(data=insurance, x='age', bins=20, edgecolor="Black")
ax.set_title("A Histogram of the age counts")
```
![A histogram of age counts](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/5ed055e4-a277-4901-8a5b-5a8b23d07d36)
 ### The histogram shows that the ages less than 20 got the highest count of the insurance cover

# Barplots
```
fig, ax = plt.subplots()
sns.barplot(data=insurance, y='charges', x = 'smoker',estimator='mean')
ax.set_xticklabels(['Non-Smoker', 'Smoker'], rotation=45)
ax.set_title("Barplot of smoker vs charges")
```
## A barplot of the smoker/Non-Smoker vs chargers
![Barplot of smoker vs charges](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/c128f69f-9337-4166-b596-2ebf14a2a14a)
### The barplot indictaed the the smokers had a higher charges mean compared to the non-smokers

# Boxplots
```
fig, ax =plt.subplots()
ax=sns.boxplot(data=insurance, x='smoker', y='charges')
ax.set_title("Boxplot of smoker vs. charges")
```
## A boxplot of the smoker/Non-Smoker vs Charges
![boxplot of smoker vs charges](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/22ad99e8-ea95-47c1-9c60-d8757770ab39)
###  The boxplot above shows the 25th , 50th and 75th percentiles of the insurance data , and the mean of the smoker and non-smoker group.

# CountPlots
```
fig, ax = plt.subplots()
sns.countplot(data=insurance, x='region')
ax.set_xlabel('Region')
ax.set_ylabel('Count')
ax.set_title('Count of Individuals by Region')
```
##  A count plot of individuals by region

![Countplots_of_individuals_by_region](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/7204b7b8-a8a6-40d4-b3bb-9799846ab7f7)
 ### From the countplot, we see that the southeast has the highest counts of individuals under the insurance

# Heatmaps
```
insurance_corr = insurance.corr()
ax = sns.heatmap(insurance_corr,annot=True)
ax.set_title("Heatmap of the correlations ")
```
## A heatmap of the correlations 
![heatmap_of_the_correlations](https://github.com/othinAbbey/Prediction-of-Product-Sales/assets/117769358/67619d24-b541-4f41-8e56-29a8c7dcb5fe)

### From the heatmap above we see a strong positive correlation between the smoker and charges, if an individual is a smoker the charges are higher

