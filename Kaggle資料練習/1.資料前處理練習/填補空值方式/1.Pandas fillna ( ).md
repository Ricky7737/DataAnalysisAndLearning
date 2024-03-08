## 使用fillna()手動補空值
> Python Pandas 提供 fillna( ) 的語法來補足缺失的資料
> 相關語法參考底下
```
>>> df = pd.DataFrame([[np.nan, 2, np.nan, 0],
                       [3, 4, np.nan, 1],
                       [np.nan, np.nan, np.nan, np.nan],
                       [np.nan, 3, np.nan, 4]],
                      columns=list("ABCD"))
>>> df
-------------------------------------------------------
     A    B   C    D
0  NaN  2.0 NaN  0.0
1  3.0  4.0 NaN  1.0
2  NaN  NaN NaN  NaN
3  NaN  3.0 NaN  4.0
```
#### 使用 fillna( ) 補足空值
```
>>> df.fillna(0)
     A    B    C    D
0  0.0  2.0  0.0  0.0
1  3.0  4.0  0.0  1.0
2  0.0  0.0  0.0  0.0
3  0.0  3.0  0.0  4.0
```
* 參考網站 : https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.fillna.html
