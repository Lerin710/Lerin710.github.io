---
layout: single
title: "5주차 DataFrame"
---

```python
import pandas as pd

sr = pd.Series([100, 200, 300, 400])
sr.index = ['A', 'B', 'O', 'AB']
sr
```




    A     100
    B     200
    O     300
    AB    400
    dtype: int64




```python
sr1 = pd.Series([10, 20, 30])
sr1
```




    0    10
    1    20
    2    30
    dtype: int64




```python
df = pd.DataFrame({'키':[170, 180, 175], '몸무게':[65, 78, 70]})
df.index = ['스파이더맨', '닥터스트레인지', '아이언맨']
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>키</th>
      <th>몸무게</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>스파이더맨</th>
      <td>170</td>
      <td>65</td>
    </tr>
    <tr>
      <th>닥터스트레인지</th>
      <td>180</td>
      <td>78</td>
    </tr>
    <tr>
      <th>아이언맨</th>
      <td>175</td>
      <td>70</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = pd.read_csv('scores.csv', encoding='cp949')
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>tony</td>
      <td>100.0</td>
      <td>90</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>NaN</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>bruce</td>
      <td>80.0</td>
      <td>90</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>thor</td>
      <td>50.0</td>
      <td>60</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>tony</td>
      <td>100.0</td>
      <td>90</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>NaN</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>bruce</td>
      <td>80.0</td>
      <td>90</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>thor</td>
      <td>50.0</td>
      <td>60</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.sample(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>thor</td>
      <td>50.0</td>
      <td>60</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 10 entries, 0 to 9
    Data columns (total 4 columns):
     #   Column  Non-Null Count  Dtype  
    ---  ------  --------------  -----  
     0   이름      10 non-null     object 
     1   국어      9 non-null      float64
     2   영어      10 non-null     int64  
     3   수학      9 non-null      float64
    dtypes: float64(2), int64(1), object(1)
    memory usage: 448.0+ bytes
    


```python
df.shape
```




    (10, 4)




```python
len(df)
```




    10




```python
df.isnull().sum()
```




    이름    0
    국어    1
    영어    0
    수학    1
    dtype: int64




```python
df_dropna = df.dropna()
df_dropna
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>tony</td>
      <td>100.0</td>
      <td>90</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>bruce</td>
      <td>80.0</td>
      <td>90</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_fillna = df.fillna(50)
df_fillna
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>tony</td>
      <td>100.0</td>
      <td>90</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>50.0</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>bruce</td>
      <td>80.0</td>
      <td>90</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>thor</td>
      <td>50.0</td>
      <td>60</td>
      <td>50.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>9.000000</td>
      <td>10.000000</td>
      <td>9.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>86.111111</td>
      <td>82.500000</td>
      <td>78.888889</td>
    </tr>
    <tr>
      <th>std</th>
      <td>16.914819</td>
      <td>21.114766</td>
      <td>17.638342</td>
    </tr>
    <tr>
      <th>min</th>
      <td>50.000000</td>
      <td>35.000000</td>
      <td>55.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>80.000000</td>
      <td>76.250000</td>
      <td>65.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>90.000000</td>
      <td>90.000000</td>
      <td>75.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>100.000000</td>
      <td>98.750000</td>
      <td>95.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>100.000000</td>
      <td>100.000000</td>
      <td>100.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['국어'].sum()
```




    775.0




```python
df.value_counts('영어')
```




    영어
    100    3
    90     2
    35     1
    60     1
    75     1
    80     1
    95     1
    dtype: int64




```python
df['국어']
```




    0    100.0
    1     90.0
    2     95.0
    3    100.0
    4      NaN
    5     70.0
    6     80.0
    7     50.0
    8    100.0
    9     90.0
    Name: 국어, dtype: float64




```python
df[['국어', '영어']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>국어</th>
      <th>영어</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>100.0</td>
      <td>90</td>
    </tr>
    <tr>
      <th>1</th>
      <td>90.0</td>
      <td>80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>95.0</td>
      <td>100</td>
    </tr>
    <tr>
      <th>3</th>
      <td>100.0</td>
      <td>100</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>35</td>
    </tr>
    <tr>
      <th>5</th>
      <td>70.0</td>
      <td>75</td>
    </tr>
    <tr>
      <th>6</th>
      <td>80.0</td>
      <td>90</td>
    </tr>
    <tr>
      <th>7</th>
      <td>50.0</td>
      <td>60</td>
    </tr>
    <tr>
      <th>8</th>
      <td>100.0</td>
      <td>100</td>
    </tr>
    <tr>
      <th>9</th>
      <td>90.0</td>
      <td>95</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[1]
```




    이름     sam
    국어    90.0
    영어      80
    수학    75.0
    Name: 1, dtype: object




```python
df.loc[[1,2,3]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[2]
```




    이름    vision
    국어      95.0
    영어       100
    수학     100.0
    Name: 2, dtype: object




```python
df.iloc[2:5]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>NaN</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 시퀀스가 아니라 인덱스로 추출
df.loc[2:5]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>NaN</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>이름</th>
      <th>국어</th>
      <th>영어</th>
      <th>수학</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>tony</td>
      <td>100.0</td>
      <td>90</td>
      <td>95.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>sam</td>
      <td>90.0</td>
      <td>80</td>
      <td>75.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vision</td>
      <td>95.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>peter</td>
      <td>100.0</td>
      <td>100</td>
      <td>100.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>scott</td>
      <td>NaN</td>
      <td>35</td>
      <td>60.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>tor</td>
      <td>70.0</td>
      <td>75</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>bruce</td>
      <td>80.0</td>
      <td>90</td>
      <td>55.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>thor</td>
      <td>50.0</td>
      <td>60</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8</th>
      <td>steaven</td>
      <td>100.0</td>
      <td>100</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>wanda</td>
      <td>90.0</td>
      <td>95</td>
      <td>70.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[1,3]
```




    75.0




```python
df.iloc[1:3, 1:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>국어</th>
      <th>영어</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>90.0</td>
      <td>80</td>
    </tr>
    <tr>
      <th>2</th>
      <td>95.0</td>
      <td>100</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
