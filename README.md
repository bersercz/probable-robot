# Covid 2019 Data Analysis

# About Dataset 
### The dataset contains worldwide COVID-19 statistics up to April 2020, covering confirmed cases, deaths, and recoveries across different regions. Basic cleaning was done to remove irrelevant or incomplete records, making the data ready for analysis.

## Data Cleaning & Analyzing
```python
covid.shape
covid.columns
covid.dtypes
covid.count()
covid.isnull().sum()
sns.heatmap(covid.isnull())
covid.info
```

# Problem Statements & Solutions

## 1) Show the number of confirnmed, Deaths and Recovered cases in each regions
```python
covid.groupby('Region') [['Confirmed','Deaths','Recovered']].sum()
```

## 2) Remove the cases where Confirmed cases are less then 10
```python
(covid['Confirmed'] < 10).sum()
covid_1 = covid[~(covid.Confirmed < 10)]
```

## 3) In which Region, maximum number of Confirmed cases were recorded ?
```python
covid.groupby('Region') ['Confirmed'].max().sort_values(ascending = False).head(10)
```

## 4) In which Region, minimum number of Deaths cases were recorded ?
```python
covid.groupby('Region').Deaths.sum().sort_values(ascending = True).head(50)
```

## 5) How many Confirmed , Deaths & Recovered cases were reported from India till 29 April 2020 ?
```python 
   data[data.Region == 'India']
```

## 6-A ) Sort the entire data wrt No. of Confirmed cases in ascending order.
```python
covid.sort_values(by =['Confirmed'], ascending = True).head(50)
```

## 6-B ) Sort the entire data wrt No. of Recovered cases in descending order.
```python 
covid.sort_values(by = ['Recovered'] , ascending = False).head(50)
```

# Findings
### 1. The pandemic showed uneven spread across regions, with some heavily affected and others reporting comparatively fewer cases.
### 2. Recovery numbers varied widely, reflecting differences in healthcare systems and response effectiveness.
### 3. Mortality rates were not uniform, suggesting factors like infrastructure, preparedness, and demographics influenced outcomes.
### 4. India’s data showed a significant presence of cases but also notable recoveries during the observed period.
### 5. Sorting and aggregating the data highlighted global trends and regional contrasts in COVID-19 impact.


# Conclusion

### The analysis demonstrated that COVID-19 affected regions differently, both in severity and recovery. It highlighted the importance of timely data cleaning and organization to identify trends, compare regions, and better understand the global progression of the pandemic.

# Project By : Devansh Singh Tomar
