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
  - 使用字典資料型態傳入pandas.Series()
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
