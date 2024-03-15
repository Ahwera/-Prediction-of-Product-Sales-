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
### Import libraries
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

![Unknown-2](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/b7d9ab6d-12b1-4582-8beb-d7f462337f43)


##  A histogram Showing the Charges
```
ax = sns.histplot(data=insurance, x='charges', bins=10, edgecolor="Black")
ax.set_title("A Histogram of the Charges")
```

### The histogram shows the count of the charges , we see that the count (10-15000) have the highest counts
![Unknown-3](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/6e7f8e8c-2b34-4778-b62b-62638233eec3)

##  A Histogram showing the age counts 
```
ax = sns.histplot(data=insurance, x='age', bins=20, edgecolor="Black")
ax.set_title("A Histogram of the age counts")
```
![Unknown-4](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/3e70ae8c-e61b-4953-adeb-7c75824a446b)

 ### The histogram shows that the ages less than 20 got the highest count of the insurance cover

# Barplots
```
fig, ax = plt.subplots()
sns.barplot(data=insurance, y='charges', x = 'smoker',estimator='mean')
ax.set_xticklabels(['Non-Smoker', 'Smoker'], rotation=45)
ax.set_title("Barplot of smoker vs charges")
```
## A barplot of the smoker/Non-Smoker vs chargers
![Unknown-5](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/246fdd0e-670a-48f6-8a17-1614ba6dfa8a)


### The barplot indictaed the the smokers had a higher charges mean compared to the non-smokers

# Boxplots
```
fig, ax =plt.subplots()
ax=sns.boxplot(data=insurance, x='smoker', y='charges')
ax.set_title("Boxplot of smoker vs. charges")
```
## A boxplot of the smoker/Non-Smoker vs Charges
![Unknown-6](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/2d899140-20d9-444c-a75c-b317db6b9da6)


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
![Unknown-7](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/942f5632-6cbf-4de4-9f0d-fc7ae7700bf9)


 ### From the countplot, we see that the southeast has the highest counts of individuals under the insurance

# Heatmaps
```
insurance_corr = insurance.corr()
ax = sns.heatmap(insurance_corr,annot=True)
ax.set_title("Heatmap of the correlations ")
```
## A heatmap of the correlations 

![Unknown](https://github.com/Ahwera/-Prediction-of-Product-Sales-/assets/162318825/82d8deec-51f8-43ad-942c-c735744d8528)

### From the heatmap above we see a strong positive correlation between the smoker and charges, if an individual is a smoker the charges are higher

