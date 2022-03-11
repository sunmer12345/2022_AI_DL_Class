1_pandas Data Structures | pandas的資料結構 => series vs DataFrame
![image](https://github.com/sunmer12345/2022_AI_DL_Class/blob/main/series_dataframe.png)
Series vs Dataframe圖

1_1_series的運算

- 建立series
  - 使用pandas.Series()
	```
  	obj = pandas.Series([4,7,-5,3])
	obj
	```
	```
	0  4
	1  7
	2 -5
	3  3
	```
	```
	obj2 = pandas.Series([4,7,-5,3], index=['d','b','a','c'])
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
	import numpy as np
	np.exp(obj2)
	```
	```
	d   403.428793
	b   1096.633158
	a   0.006738
	c   20.085537
	dtype: float64
	```
- 搜尋滿足條件的資料
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
	```
	'b' in obj2
	```
	```
	True
	```
