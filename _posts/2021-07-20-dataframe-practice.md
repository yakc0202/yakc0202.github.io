---
title: "DataFrame 실습"
date: 2021-07-20
categories: 
 - Pandas
tags: 
- [데이터 청년 캠퍼스, Pandas]

toc: true
---
```py  
from pandas import DataFrame  
df = DataFrame({'Class': ['IoT','Network', 'Economy','Big Data', 'Cloud'],  
                       'Year': [2018, 2017, 2018, 2018, 2019],  
                       'Price': [100, 125, 132, 312, 250],  
                       'Location': ['Korea','Korea', 'Korea', 'US','Korea']},  
                      index=['C01','C02','C03', 'C04', 'C05'])  
```  
## 'Year'컬럼만 선택  
- Series  
  * ```py  
    df.Year  
    ```  
  * ```py  
    df['Year']  
    ```  
    
- DataFrame  
  * ```py  
    df[['Year']]  
    ```  

## 'Class' 와 'Location' 컬럼만 선택  

```py  
df[['Class', 'Location']]  
```  

## C01과 C03 강의의 모든 컬럼 선택  

```py  
df.loc[['C01', 'C03']]  
```  

## C01 ~ C03 강의의 'Class'와 'Price'만 선택  

```py  
df.loc['C01':'C03', ['Class','Price']]  
```  

## 2019년도 강의만 조회  

```py  
df[df.Year == 2019]  
```  

## 가장 가격이 비싼 강의 정보만 조회  

```py  
df[df.Price == df.Price.max()]  
```  

## 2018, 2019년도에 개설된 강의 조회  

- ```py  
  df[(df.Year == 2018) | (df.Year == 2019)]  
  ```  
- ```py  
  df.Year.isin([2018, 2019])  
  ```  
## 2018년도에 한국에서 개설된 강의 조회  

```py  
df[(df.Location=='Korea') & (df.Year==2018)]  
```  

