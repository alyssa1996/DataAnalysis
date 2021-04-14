# DataAnalysis
## 분석 내용 소개
### [Happiness Analysis](https://github.com/alyssa1996/DataAnalysis/blob/main/Happiness%20Analysis.ipynb)
> 이 분석은 행복지수가 높은 나라를 분석하고 어느 요인에 의해 행복지수가 달라지는 지 알아보기 위해 시작하였다.
### [South Korea Visitors Analysis](https://github.com/alyssa1996/DataAnalysis/blob/main/South%20Korea%20Vistiors.ipynb)
> 2019년 1월부터 202년 4월까지 한국을 방문한 외국인들의 특성들을 포함한 데이터를 분석한다.

<br></br>
## 분석 도구 공부 내용 정리 및 요약 
### Pandas DataFrame 사용하기
#### #1 사전 데이터타입을 DataFrame으로 변환하기
```python
import pandas as pd
ex_dict={'Korea':1,'China':2,'Japan':3,'Usa':4}

ex_dt=pd.DataFrame(list(ex_dict.items()),columns=['Country','Random N'])
ex_dt

>>>	Country	Random N
0	Korea	1
1	China	2
2	Japan	3
3	Usa	4
```
* 이와 같은 형식은 사전의 '키'와 '값'이 하나의 행으로서 처리되고, 각 행의 열 이름을 따로 지정해주는 방식으로 사전을 DataFrame으로 변환한다.<br>
참고 자료: https://www.delftstack.com/ko/howto/python-pandas/how-to-convert-python-dictionary-to-pandas-dataframe/

<br></br>
#### #2 DataFrame 정렬 : DataFrame.sort_values()
**인자 목록**
1. by=기준 변수 : 정렬할 기준 변수(axis=0 이면 by='칼럼이름', axis=1이면 by='row번호')
2. axis=0 / axis=1 : default=0
3. ascending=True(오름차순) / ascending=False(내림차순) : default=True
4. inplace=False: default=False, True로 설정하면 정렬된 결과가 DataFrame에 적용되어 반환됨.
```python
result.sort_values(by='sum of visitor',ascending=False,inplace=True)
```

<br></br>
#### #3 DataFrame 인덱스 재정렬 : DataFrame.reset_index(drop=True)
* 인자로 inplace=True를 삽입하면 인덱스가 재정렬된 결과가 DataFrame에 바로 적용되어 반환됨
* 인덱스 재정렬은 주로 DataFrame을 특정 기준에 맞춰 정렬한 뒤, 그 반환값의 인덱스를 다시 오름차순으로 정리하기 위해 사용함
* [참고자료](https://specialscene.tistory.com/44)
```python
result.reset_index(drop=True,inplace=True)
```
