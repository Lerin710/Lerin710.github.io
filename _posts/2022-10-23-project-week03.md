```python
strVal = 'data science'               # 문자열 변수
nVal = 12345                          # 정수형 변수
fVal = 1.2                            # 실수형 변수
lVal = ['data', 'science']            # 리스트
dVal = {'lecture' : 'data science'}   # 딕셔너리
bVal = True                           # 논리형 변수(참/거짓)
```


```python
# 기본적인 주석
```


```python

''' 
이런 형태의 주석도 많이 사용
'''
```




    ' \n이런 형태의 주석도 많이 사용\n'




```python
strVal
```




    'data science'




```python
nVal
```




    12345




```python
fVal
```




    1.2




```python
lVal
```




    ['data', 'science']




```python
dVal
```




    {'lecture': 'data science'}




```python
bVal
```




    True




```python
print('strVal : ', strVal)
print('nVal : ', nVal)
print('fVal : ', fVal)
print('lVal : ', lVal)
print('dVal : ', dVal)
print('bVal : ', bVal)
```

    strVal :  data science
    nVal :  12345
    fVal :  1.2
    lVal :  ['data', 'science']
    dVal :  {'lecture': 'data science'}
    bVal :  True
    


```python
print('strVal : ', type(strVal))
print('nVal : ', type(nVal))
print('fVal : ', type(fVal))
print('lVal : ', type(lVal))
print('dVal : ', type(dVal))
print('bVal : ', type(bVal))
```

    strVal :  <class 'str'>
    nVal :  <class 'int'>
    fVal :  <class 'float'>
    lVal :  <class 'list'>
    dVal :  <class 'dict'>
    bVal :  <class 'bool'>
    


```python
'''
같은 변수명일 경우, 이전 데이터를 덮어씀
'''
nVal = 16                          # 정수형 변수
fVal = 3.14                        # 실수형 변수
```


```python
print('10진수 표현 : ', nVal)       # 10진수
print('2진수 표현 : ', bin(nVal))  # 2진수
print('8진수 표현 : ', oct(nVal))  # 8진수
print('16진수 표현 : ', hex(nVal))  # 16진수
```

    10진수 표현 :  16
    2진수 표현 :  0b10000
    8진수 표현 :  0o20
    16진수 표현 :  0x10
    


```python
btVal = True                           # 논리형 변수(참)
bfVal = False                          # 논리형 변수(거짓)
```


```python
btVal = TRUE                          # 논리형 변수(참) - 오류
bfVal = FALSE                          # 논리형 변수(거짓) - 오류
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_14284\2634659662.py in <module>
    ----> 1 btVal = TRUE                          # 논리형 변수(참) - 오류
          2 bfVal = FALSE                          # 논리형 변수(거짓) - 오류
    

    NameError: name 'TRUE' is not defined



```python
btVal = true                          # 논리형 변수(참) - 오류
bfVal = false                          # 논리형 변수(거짓) - 오류
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_14284\2305073268.py in <module>
    ----> 1 btVal = true                          # 논리형 변수(참) - 오류
          2 bfVal = false                          # 논리형 변수(거짓) - 오류
    

    NameError: name 'true' is not defined



```python
10 == 11
```




    False




```python
10 != 11
```




    True




```python
10 >= 11
```




    False




```python
10 <= 11
```




    True




```python
10 > 11
```




    False




```python
10 < 11
```




    True




```python
nBig = 100
nSmall = 10
```


```python
print(nBig == nSmall)
print(nBig != nSmall)
print(nBig >= nSmall)
print(nBig <= nSmall)
print(nBig > nSmall)
print(nBig < nSmall)
```

    False
    True
    True
    False
    True
    False
    


```python
print(nBig =< nSmall)     # 오류
```


      File "C:\Users\user\AppData\Local\Temp\ipykernel_14284\2910044186.py", line 1
        print(nBig =< nSmall)     # 오류
                    ^
    SyntaxError: invalid syntax
    



```python
print(nBig => nSmall)     # 오류
```


      File "C:\Users\user\AppData\Local\Temp\ipykernel_14284\1053890005.py", line 1
        print(nBig => nSmall)     # 오류
                    ^
    SyntaxError: invalid syntax
    



```python
strData = 'data'               # 문자열 변수
strSci = "Science"             # 문자열 변수
```


```python
strLecture = strData + strSci
```


```python
strLecture
```




    'dataScience'




```python
strLecture = strData +" "+ strSci
strLecture
```




    'data Science'




```python
strLecture.split()              # split()으로 공백을 기준으로 문자열 구분
```




    ['data', 'Science']




```python
lSeperate = strLecture.split() # split()으로 공백을 기준으로 문자열 구분하여 lSeperate 변수에 저장
```


```python
type(lSeperate)
```




    list




```python
strHello = "안녕하세요. 반갑습니다."
```


```python
strHello.find("반갑")       # 문자열을 찾기 위해 find() 함수를 이용
                            # 문자열을 있으면, 첫번째 시작 인덱스를 반환
```




    7




```python
strHello.find("hello")    # 문자열이 없으면, -1을 리턴
```




    -1




```python
"반갑" in strHello          # in 명령어를 사용하여 확인 가능 : if 조건문에서 활용
```




    True




```python
strHello.replace('.', '?')    # .을 모두 ?로 변경
```




    '안녕하세요? 반갑습니다?'




```python
strHello.replace('.', '?')                  
strHello.replace("하세요", "하셔유")       # 안녕하셔유? 가 될까요?
```




    '안녕하셔유. 반갑습니다.'




```python
strHello                      # 원본 데이터는 변하지 않음
```




    '안녕하세요. 반갑습니다.'




```python
strNewHello = strHello.replace('.', '?')                    # strHello를 replace하여 strNewHello에 저장   
strNewHello = strNewHello.replace("하세요", "하셔유")       # strNewHello를 replace하여 strNewHello에 저장
strNewHello
```




    '안녕하셔유? 반갑습니다?'




```python
strHello.strip('반갑습니다.')    # strip()함수를 이용하여 "반갑습니다."를 제거
```




    '안녕하세요. '




```python
strHello                    # 역시 원본 데이터는 변하지 않음
```




    '안녕하세요. 반갑습니다.'




```python
lnData = [1,2,3,4,5]     # lnData를 리스트로 생성
print(lnData)
print('type : ', type(lnData))
```

    [1, 2, 3, 4, 5]
    type :  <class 'list'>
    


```python
print(lnData[0])    # lnData 리스트의 0번 인덱스의 값 출력
print(lnData[3])    # lnData 리스트의 3번 인덱스의 값 출력
```

    1
    4
    


```python
lnData[0] = lnData[4]   # lnData[4]의 값을 lnData[0]에 저장
print(lnData)           # lnData 리스트를 출력
```

    [5, 2, 3, 4, 5]
    


```python
print(lnData[2:4])      # lnData[4]에 저장된 5는 출력되지 않음
```

    [3, 4]
    


```python
lnData = [1,2,3,4,5]
lstrData=['a', 'b', 'c']

# 두 개의 서로다른 자료형을 가진 리스트를 병합
lnData + lstrData
```




    [1, 2, 3, 4, 5, 'a', 'b', 'c']




```python
lnData.append(10)   # 10을 맨 뒤에 추가
lnData
```




    [1, 2, 3, 4, 5, 10]




```python
lnData.insert(0, 'python')  #'python'문자열을 0번 인덱스에 추가하고, 기존 인덱스에 저장된 데이터는 하나씩 뒤로 밀림(인덱스가 +1 추가)
lnData
```




    ['python', 1, 2, 3, 4, 5, 10]




```python
lnData.remove('python')     # 'python' 데이터를 삭제
lnData
```




    [1, 2, 3, 4, 5, 10]




```python
del lnData[5]              # del 명령어를 통해 인덱스를 지정하여 삭제
lnData
```




    [1, 2, 3, 4, 5]




```python
lnData
```




    [1, 2, 3, 4, 5]




```python
lnData.pop(0)     # 0번 인덱스의 데이터를 삭제
lnData
```




    [2, 3, 4, 5]




```python
lnData.pop()     # 인덱스 지정이 없으면, 마지막 인덱스의 값을 삭제
lnData
```




    [2, 3, 4]




```python
lnData.clear()  # 리스트의 모든 데이터를 삭제
lnData
```




    []




```python
# 튜플의 기본 구조
tVal = ("사과", "딸기", "바나나", "토마토", "키위")

print(tVal)
print(type(tVal))
```

    ('사과', '딸기', '바나나', '토마토', '키위')
    <class 'tuple'>
    


```python
# 튜플에 저장된 데이터는 변경이 불가능
tVal[0] = "포도"
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_14284\2072098934.py in <module>
          1 # 튜플에 저장된 데이터는 변경이 불가능
    ----> 2 tVal[0] = "포도"
    

    TypeError: 'tuple' object does not support item assignment



```python
# count() 함수를 이용하여 튜플에 저장된 특정 데이터의 개수를 확인
tData = ( 1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7)
tData.count(1)
```




    3




```python
# len()함수를 이용하여 튜플에 저장된 전체 데이터 개수를 확인
len(tVal)
```




    5




```python
len(tData)
```




    11




```python
print(tData[2:5])
```

    (3, 1, 2)
    


```python
tTuple = tVal+ tData
print(tTuple)
```

    ('사과', '딸기', '바나나', '토마토', '키위', 1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7)
    


```python
tData * 2
```




    (1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7, 1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7)




```python
tData
```




    (1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7)




```python
tData2 = tData * 2
print(tData2)
```

    (1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7, 1, 2, 3, 1, 2, 3, 4, 5, 1, 2, 7)
    


```python
print("tVal memory = ", hex(id(tVal)))
tVal = tVal * 2
print("tVal memory = ", hex(id(tVal)))
print(tVal)
```

    tVal memory =  0x19651b414a0
    tVal memory =  0x19651c917c0
    ('사과', '딸기', '바나나', '토마토', '키위', '사과', '딸기', '바나나', '토마토', '키위')
    


```python
print("tVal memory = ", hex(id(tVal)))
tVal = tVal + tVal
print("tVal memory = ", hex(id(tVal)))
print(tVal)
```

    tVal memory =  0x19651c917c0
    tVal memory =  0x19651c81930
    ('사과', '딸기', '바나나', '토마토', '키위', '사과', '딸기', '바나나', '토마토', '키위', '사과', '딸기', '바나나', '토마토', '키위', '사과', '딸기', '바나나', '토마토', '키위')
    


```python
sVal = {1, 2, 3, 4, 5}
print(sVal)
print(type(sVal))
```

    {1, 2, 3, 4, 5}
    <class 'set'>
    


```python
sVal[1:2]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_14284\468339363.py in <module>
    ----> 1 sVal[1:2]
    

    TypeError: 'set' object is not subscriptable



```python
# add 함수를 이용하여 데이터를 추가할 수 있음
sVal.add(100)
print(sVal)
```

    {1, 2, 3, 4, 5, 100}
    


```python
# update 함수를 이용하여 여러개의 데이터를 추가할 수 있음
sVal.update([200, 300])
print(sVal)
```

    {1, 2, 3, 4, 5, 100, 200, 300}
    


```python
# remove 함수를 이용하여 데이터를 삭제할 수 있음
sVal.remove(200)
print(sVal)
```

    {1, 2, 3, 4, 5, 100, 300}
    


```python
# clear() 함수를 이용하여 데이터를 초기화 할 수 있음
sVal.clear()
print(sVal)
```

    set()
    


```python
sVal = {100, 200, 300, 400, 500}
sData = {"a", "b", "c", "c", 100, 300}
print(sVal)
print(sData)
```

    {400, 100, 500, 200, 300}
    {'a', 100, 300, 'b', 'c'}
    


```python
# intersection() 함수를 이용하여 교집합을 만들 수 있음
sVal.intersection(sData)
```




    {100, 300}




```python
# deference() 함수를 이용하여 차집합을 만들 수 있음
sVal.difference(sData)
```




    {200, 400, 500}




```python
# "-" 연산자로도 가능
sVal - sData
```




    {200, 400, 500}




```python
# union() 함수를 이용하여 합집합을 만들 수 있음
sVal.union(sData)
```




    {100, 200, 300, 400, 500, 'a', 'b', 'c'}




```python
# "+"연산자는 불가능
sVal + sData
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_14284\3037826460.py in <module>
          1 # "+"연산자는 불가능
    ----> 2 sVal + sData
    

    TypeError: unsupported operand type(s) for +: 'set' and 'set'



```python
# symetric_difference()를 이용하여 합집합에서 교집합을 뺀 집합을 만들 ㅅ ㅜ있음
sVal.symmetric_difference(sData)
```




    {200, 400, 500, 'a', 'b', 'c'}




```python
# 딕셔너리 기본 구조는 다음과 같이 표현할 수 있음
dVal = {
    'name' : '이컴공',
    'email' : 'computer@hoseo.edu',
    'address' : '충남 아산시'
}
print(dVal)
print(type(dVal))
```

    {'name': '이컴공', 'email': 'computer@hoseo.edu', 'address': '충남 아산시'}
    <class 'dict'>
    


```python
dData = {
    "사과" : 300, 
    "포도" : 200, 
    "배" : 500,
    "키위" : 100
}
```


```python
# 키를 이용한 항목 검색
print(dData["배"])
```

    500
    


```python
# get() 함수를 이용한 항목 검색
dData.get("배")
```




    500




```python
# 새로운 키 추가를 통한 항목 추가
dData["딸기"] = 100
print(dData)
```

    {'사과': 300, '포도': 200, '배': 500, '키위': 100, '딸기': 100}
    


```python
# pop을 이용한 항목 삭제
dData.pop("사과")
```




    300




```python
dData
```




    {'포도': 200, '배': 500, '키위': 100, '딸기': 100}




```python
dData.pop()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    ~\AppData\Local\Temp\ipykernel_14284\2765138924.py in <module>
    ----> 1 dData.pop()
    

    TypeError: pop expected at least 1 argument, got 0



```python
# sorted 함수를 이용한 정렬
sorted(dData)
```




    ['딸기', '배', '키위', '포도']




```python
# sorted와 values 함수를 이용하여 값을 정렬할 수 있음
sorted(dData.values())
```




    [100, 100, 200, 500]




```python
# 실제 dData는 변화가 없음
dData
```




    {'포도': 200, '배': 500, '키위': 100, '딸기': 100}




```python
# 함수 f(x)를 생성하고 x 값을 입력으로 받음
def f(x):
  # x에 10을 더한 값을 출력
  return x + 10
```


```python
f(2)
```




    12




```python

```
