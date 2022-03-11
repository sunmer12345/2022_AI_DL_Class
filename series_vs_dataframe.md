1_pandas Data Structures | pandas的資料結構 => series vs DataFrame
![image](https://github.com/sunmer12345/2022_AI_DL_Class/blob/main/series_dataframe.png)
Series vs Dataframe圖

1_1_series的運算

- 建立series
  - 使用pandas.Series()
	```
  	obj = pandas.Series([4,7,-5,3])  // 建立 index
	obj
	```
	```
	0  4
	1  7
	2 -5
	3  3
	```
	```
	obj2 = pandas.Series([4,7,-5,3], index=['d','b','a','c'])  // 建立指定 index 的 label
	obj2
	```
	```
	d  4
	b  7
	a -5
	c  3
	```
  - 使用字典資料型態傳入pandas.Series()
  	```
	import numpy as np  // 長度固定有順序的 dict，從 index 映射到 value
	np.exp(obj2)
	```
	```
	d   403.428793
	b   1096.633158
	a   0.006738
	c   20.085537
	dtype: float64
	```
	```
	sdata = {'Ohio': 35000, 'Texas': 71000, 'Oregon':16000, 'Utah': 5000}  // 字典資料型態建立 series
	obj3 = pandas.Series(sdata)
	obj3
	```
	```
	Ohio    35000
	Oregon  16000
	Texas	71000
	Utah	 5000
	dtype: int64
	```
- 搜尋滿足條件的資料
  - 對應的查詢方式
	```
	obj2['a']
	```
	```
	-5
	```
	```
	obj2[['c','a','d']]
	```
	```
	c  3
	a -5
	d  6
	dtype: int64
	```
	```
	obj2[obj2 > 0]
	```
	```
	d  6
	b  7
	c  3
	dtype: int64
	```
	```
	obj2 * 2
	```
	```
	d  12
	b  14
	a -10
	c   6
	dtype: int64
	```
  - 字典資料型態查詢方式
	```
	'b' in obj2
	```
	```
	True
	```
	```
	'e' in obj2
	```
	```
	False
	```
	```
	states = ['California', 'Ohio', 'Oregon', 'Texas']  // 自行建立搜尋的順序
	obj4 = pandas.Series(sdata, index=states)
	obj4
	```
	```
	California   NaN
	Ohio	 35000.0
	Oregon	 16000.0
	Texas	 71000.0
	dtype: float64
	```
	```
	pandas.isnull(obj4)  // 判斷值是否不存在，不存在回傳 True，反之回傳 False
	```
	```
	California	True
	Ohio		False
	Oregon		False
	Texas		False
	dtype: bool
	```
	```
	pandas.notnull(obj4)  // 判斷值是否存在，存在回傳 True，反之回傳 False
	```
	```
	California	False
	Ohio		True
	Oregon		True
	Texas		True
	dtype: bool
	```
1_2_DataFrame的運算
- 建立DataFrame
  - 使用 pandas.DataFrame()
  	```
  	data = {'state': ['Ohio', 'Ohio', 'Ohio', 'Nevada', 'Nevada', 'Nevada'], 
        'year': [2000, 2001, 2002, 2001, 2002, 2003], 
        'pop': [1.5, 1.7, 3.6, 2.4, 2.9, 3.2]}
	
	frame = pandas.DataFrame(data)
	frame
	```
	```
		pop	state	year
	0	1.5	Ohio	2000
	1	1.7	Ohio	2001
	2	3.6	Ohio	2002
	3	2.4	Nevada	2001
	4	2.9	Nevada	2002
	5	3.2	Nevada	2003
	```
  - 使用字典資料型態傳入 pandas.DataFrame()
- 搜尋滿足條件的資料
