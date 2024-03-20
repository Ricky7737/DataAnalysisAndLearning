# 正規表達式-REGXP
> REGEXP 可以用來快速提取篩選匹配出符合條件的資料，放在子句裡設定條件
> 語法為
```
SELECT columns1, columns2 .....
FROM TABLE
WHERE 目標欄位 REGEXP 條件 ```
```
## REGEXP 語法
```
1.  ^：匹配字串的開頭。
2.  $：匹配字串的結尾。
3.  .：匹配任何單個字符。
4.  []：匹配方括號內的任何一個字符。
5.  [^]：否定方括號內的字符集。
6.  *：匹配前面的子表達式零次或多次。
7.  +：匹配前面的子表達式一次或多次。
8.  ?：匹配前面的子表達式零次或一次。
9.  {n}：匹配前面的子表達式恰好 n 次。
10. {n,}：匹配前面的子表達式至少 n 次。
11. {n,m}：匹配前面的子表達式至少 n 次，但不超過 m 次。
12. \：用於轉義下一個字符，使其不被解釋為特殊字符。
```
## 這邊以 hankrank basic select 系列題目作範例
### 1. 找尋開頭為 aeiou 的城市名稱使用 `^`
> MYSQL
```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU]';
```
> ^[aeiouAEIOU] 中的 ^ 表示已開頭字母下去搜尋符合有 aeiou 的名稱

### 2. 找尋開頭為 aeiou 的城市名稱使用 `$`
```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU]';
```
> [aeiouAEIOU]$ 中的 ^ 表示已開頭字母下去搜尋符合有 aeiou 的名稱

### 參考資料 : 
[1] : MYSQL 正規表達式操作 : https://www.itread01.com/study/mysql-regexp.html
