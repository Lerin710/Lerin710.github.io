```python
# 내장함수 예 : input
strText = input("아무 문장이나 입력하세요 : ")
print(strText)
```

    아무 문장이나 입력하세요 : 안녕하세요
    안녕하세요
    


```python
# List를 이용한 다차원 배열
flVal = [1.0, 2.0, 3.14, 4.2, 5.1]  # 실수 list를 생성
```


```python
# flVal 3개를 리스트로 구성하여 arVal 다차원 배열을 생성
arVal = [flVal, flVal, flVal]
arVal
```




    [[1.0, 2.0, 3.14, 4.2, 5.1],
     [1.0, 2.0, 3.14, 4.2, 5.1],
     [1.0, 2.0, 3.14, 4.2, 5.1]]




```python
# arVal은 다차원 배열이므로, arVal[n] 인덱스 연산을 통해 n차원 배열 값을 출력
arVal[0]
```




    [1.0, 2.0, 3.14, 4.2, 5.1]




```python
arVal[1]
```




    [1.0, 2.0, 3.14, 4.2, 5.1]




```python
arVal[1][2]
```




    3.14




```python
# 1 차원 값을 변환하여 다른 값을 대입 했을때의 다차원 배열
arVal[0] = 'python'
arVal
```




    ['python', [1.0, 2.0, 3.14, 4.2, 5.1], [1.0, 2.0, 3.14, 4.2, 5.1]]




```python
arVal[0][2]
```




    't'




```python
arVal[0] = 'python programming'
arVal
```




    ['python programming', [1.0, 2.0, 3.14, 4.2, 5.1], [1.0, 2.0, 3.14, 4.2, 5.1]]




```python
# numpy 패치지를 import 
import numpy as np
arData = np.array([1.0, 2.0, 3.14, 4.2, 5.1])
arData
```




    array([1.  , 2.  , 3.14, 4.2 , 5.1 ])




```python
# 배열 각 요소의 합을 출력
arData.sum()
```




    15.44




```python
arVal.sum()
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_4708\2999335311.py in <module>
    ----> 1 arVal.sum()
    

    AttributeError: 'list' object has no attribute 'sum'



```python
print(type(arVal))
print(type(arData))
```

    <class 'list'>
    <class 'numpy.ndarray'>
    


```python
# 배열에 대한 표준편차 출력
arData.std()
```




    1.4717934637713266




```python
# 배열의 누적 합을 출력
arData.cumsum()
```




    array([ 1.  ,  3.  ,  6.14, 10.34, 15.44])




```python
arData * 2
```




    array([ 2.  ,  4.  ,  6.28,  8.4 , 10.2 ])




```python
arData ** 2 # 2를 제곱
```




    array([ 1.    ,  4.    ,  9.8596, 17.64  , 26.01  ])




```python
# 루트를 적용한 값을 출력
np.sqrt(arData)
```




    array([1.        , 1.41421356, 1.77200451, 2.04939015, 2.25831796])




```python
arVal = np.array([arData, arData ** 2])
arVal
```




    array([[ 1.    ,  2.    ,  3.14  ,  4.2   ,  5.1   ],
           [ 1.    ,  4.    ,  9.8596, 17.64  , 26.01  ]])




```python
arVal.sum(axis=0) # 축(axis)이 0일 경우 세로 축의 합을 출력
```




    array([ 2.    ,  6.    , 12.9996, 21.84  , 31.11  ])




```python
arVal.sum(axis=1) # 축(axis)이 0일 경우 가로 축의 합을 출력
```




    array([15.44  , 58.5096])




```python
# NumPy.array를 사용한 코드
np.array([[0,0,0],[0,0,0]])
```




    array([[0, 0, 0],
           [0, 0, 0]])




```python
# NumPy.zeros를 사용한 코드
arZero = np.zeros((2,3), dtype = 'i') 
arZero
```




    array([[0, 0, 0],
           [0, 0, 0]], dtype=int32)




```python
# pandas import
import pandas as pd

pandas_series = pd.Series([30, 20, 10], index=['국어', '영어', '수학'])
print(type(pandas_series))
pandas_series
```

    <class 'pandas.core.series.Series'>
    




    국어    30
    영어    20
    수학    10
    dtype: int64




```python
pandas_series[1:]
```




    영어    20
    수학    10
    dtype: int64




```python
pandas_series[0]
```




    30




```python
pandas_series[0][1]
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_4708\3046292380.py in <module>
    ----> 1 pandas_series[0][1]
    

    IndexError: invalid index to scalar variable.



```python
df = pd.DataFrame([30,20,10], columns=['score'], index=['국어', '영어', '수학'])
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
      <th>score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>국어</th>
      <td>30</td>
    </tr>
    <tr>
      <th>영어</th>
      <td>20</td>
    </tr>
    <tr>
      <th>수학</th>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>




```python
# DataFrame의 index를 표시
df.index
```




    Index(['국어', '영어', '수학'], dtype='object')




```python
# DataFrame의 column을 표시
df.columns
```




    Index(['score'], dtype='object')




```python
# DataFrame의index 중에서 국어에 해당하는 값을 출력
df.loc['국어']   # ix 함수가 최근 제거되어 loc를 써야 동작
```




    score    30
    Name: 국어, dtype: int64




```python
# DataFrame의 값을 모두 합한 결과를 출력
df.sum()
```




    score    60
    dtype: int64




```python
# DataFrame의 각 colimn 값의 제곱을 출력
df.score ** 2
```




    국어    900
    영어    400
    수학    100
    Name: score, dtype: int64




```python
# DataFrame에 score2 라는 칼럼을 추가하고 값을 입력
df['score2'] = (50, 50, 50)
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
      <th>score</th>
      <th>score2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>국어</th>
      <td>30</td>
      <td>50</td>
    </tr>
    <tr>
      <th>영어</th>
      <td>20</td>
      <td>50</td>
    </tr>
    <tr>
      <th>수학</th>
      <td>10</td>
      <td>50</td>
    </tr>
  </tbody>
</table>
</div>




```python
# DataFrame 함수를 이용하여 column을 추가할 수 있음
df['score2'] = pd.DataFrame([90,90,90], index=['국어', '영어', '수학'])
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
      <th>score</th>
      <th>score2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>국어</th>
      <td>30</td>
      <td>90</td>
    </tr>
    <tr>
      <th>영어</th>
      <td>20</td>
      <td>90</td>
    </tr>
    <tr>
      <th>수학</th>
      <td>10</td>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>




```python
# column 삭제
del df['score']
```


```python
# index 를 맞추기 않았을 경우
df['score2'] = (90, 90, 90, 100)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_4708\1894884841.py in <module>
          1 # index 를 맞추기 않았을 경우
    ----> 2 df['score2'] = (90, 90, 90, 100)
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\frame.py in __setitem__(self, key, value)
       3653         else:
       3654             # set column
    -> 3655             self._set_item(key, value)
       3656 
       3657     def _setitem_slice(self, key: slice, value):
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\frame.py in _set_item(self, key, value)
       3830         ensure homogeneity.
       3831         """
    -> 3832         value = self._sanitize_column(value)
       3833 
       3834         if (
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\frame.py in _sanitize_column(self, value)
       4536 
       4537         if is_list_like(value):
    -> 4538             com.require_length_match(value, self.index)
       4539         return sanitize_array(value, self.index, copy=True, allow_2d=True)
       4540 
    

    C:\ProgramData\Anaconda3\lib\site-packages\pandas\core\common.py in require_length_match(data, index)
        555     """
        556     if len(data) != len(index):
    --> 557         raise ValueError(
        558             "Length of values "
        559             f"({len(data)}) "
    

    ValueError: Length of values (4) does not match length of index (3)



```python
# index 를 맞추기 않았을 경우
df['score2'] = pd.DataFrame([90, 90, 90, 100], index=['국어', '영어', '수학', '윤리'])
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
      <th>score2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>국어</th>
      <td>90</td>
    </tr>
    <tr>
      <th>영어</th>
      <td>90</td>
    </tr>
    <tr>
      <th>수학</th>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>




```python
# join() 함수를 이용하여 2개의 DataFrame을 하나로 합칠 수 있음
df1 = pd.DataFrame([1, 2, 3], columns = ['A'])
df2 = pd.DataFrame([10, 11, 12, 13], columns = ['B'])

df = df1.join(df2, how='outer')
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
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3.0</td>
      <td>12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>13</td>
    </tr>
  </tbody>
</table>
</div>




```python
df_inner = df1.join(df2, how='inner')
df_inner
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
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>12</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 난수를 이용한 임의의 값 생성
df = pd.DataFrame(np.random.randn(5,5))
df.columns = ['A', 'B', 'C', 'D', 'E']

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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.791724</td>
      <td>0.419364</td>
      <td>-1.577875</td>
      <td>-0.996333</td>
      <td>-0.623312</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-0.869457</td>
      <td>0.507516</td>
      <td>-0.310372</td>
      <td>-0.376604</td>
      <td>0.296590</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-0.142798</td>
      <td>1.235124</td>
      <td>0.288202</td>
      <td>0.663535</td>
      <td>-0.273286</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.420898</td>
      <td>-0.198062</td>
      <td>-0.089311</td>
      <td>-2.281557</td>
      <td>-0.470962</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.332584</td>
      <td>0.223794</td>
      <td>0.570768</td>
      <td>-0.049232</td>
      <td>-1.994702</td>
    </tr>
  </tbody>
</table>
</div>




```python
# 최대값
df.max()
```




    A    0.791724
    B    1.235124
    C    0.570768
    D    0.663535
    E    0.296590
    dtype: float64




```python
# 최소값
df.min()
```




    A   -0.869457
    B   -0.198062
    C   -1.577875
    D   -2.281557
    E   -1.994702
    dtype: float64




```python
# 평균
df.mean()
```




    A   -0.026443
    B    0.437547
    C   -0.223718
    D   -0.608038
    E   -0.613134
    dtype: float64




```python
# 표준편차
df.std()
```




    A    0.649508
    B    0.522265
    C    0.829546
    D    1.110649
    E    0.847369
    dtype: float64




```python
# 누적값
df.cumsum()
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.791724</td>
      <td>0.419364</td>
      <td>-1.577875</td>
      <td>-0.996333</td>
      <td>-0.623312</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-0.077733</td>
      <td>0.926880</td>
      <td>-1.888247</td>
      <td>-1.372937</td>
      <td>-0.326722</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-0.220530</td>
      <td>2.162004</td>
      <td>-1.600045</td>
      <td>-0.709401</td>
      <td>-0.600008</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.200367</td>
      <td>1.963941</td>
      <td>-1.689356</td>
      <td>-2.990958</td>
      <td>-1.070970</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.132217</td>
      <td>2.187736</td>
      <td>-1.118589</td>
      <td>-3.040190</td>
      <td>-3.065672</td>
    </tr>
  </tbody>
</table>
</div>




```python
# DataFrame의 통계적 요약
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>5.000000</td>
      <td>5.000000</td>
      <td>5.000000</td>
      <td>5.000000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>-0.026443</td>
      <td>0.437547</td>
      <td>-0.223718</td>
      <td>-0.608038</td>
      <td>-0.613134</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.649508</td>
      <td>0.522265</td>
      <td>0.829546</td>
      <td>1.110649</td>
      <td>0.847369</td>
    </tr>
    <tr>
      <th>min</th>
      <td>-0.869457</td>
      <td>-0.198062</td>
      <td>-1.577875</td>
      <td>-2.281557</td>
      <td>-1.994702</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>-0.332584</td>
      <td>0.223794</td>
      <td>-0.310372</td>
      <td>-0.996333</td>
      <td>-0.623312</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>-0.142798</td>
      <td>0.419364</td>
      <td>-0.089311</td>
      <td>-0.376604</td>
      <td>-0.470962</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>0.420898</td>
      <td>0.507516</td>
      <td>0.288202</td>
      <td>-0.049232</td>
      <td>-0.273286</td>
    </tr>
    <tr>
      <th>max</th>
      <td>0.791724</td>
      <td>1.235124</td>
      <td>0.570768</td>
      <td>0.663535</td>
      <td>0.296590</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Group by를 이용한 DataFrame의 그룹화
df['division'] = ['X', 'Y', 'X', 'Y', 'Z']
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
      <th>division</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.791724</td>
      <td>0.419364</td>
      <td>-1.577875</td>
      <td>-0.996333</td>
      <td>-0.623312</td>
      <td>X</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-0.869457</td>
      <td>0.507516</td>
      <td>-0.310372</td>
      <td>-0.376604</td>
      <td>0.296590</td>
      <td>Y</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-0.142798</td>
      <td>1.235124</td>
      <td>0.288202</td>
      <td>0.663535</td>
      <td>-0.273286</td>
      <td>X</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.420898</td>
      <td>-0.198062</td>
      <td>-0.089311</td>
      <td>-2.281557</td>
      <td>-0.470962</td>
      <td>Y</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.332584</td>
      <td>0.223794</td>
      <td>0.570768</td>
      <td>-0.049232</td>
      <td>-1.994702</td>
      <td>Z</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby(['division']).mean()
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
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
    <tr>
      <th>division</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>X</th>
      <td>0.324463</td>
      <td>0.827244</td>
      <td>-0.644836</td>
      <td>-0.166399</td>
      <td>-0.448299</td>
    </tr>
    <tr>
      <th>Y</th>
      <td>-0.224280</td>
      <td>0.154727</td>
      <td>-0.199842</td>
      <td>-1.329080</td>
      <td>-0.087186</td>
    </tr>
    <tr>
      <th>Z</th>
      <td>-0.332584</td>
      <td>0.223794</td>
      <td>0.570768</td>
      <td>-0.049232</td>
      <td>-1.994702</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
