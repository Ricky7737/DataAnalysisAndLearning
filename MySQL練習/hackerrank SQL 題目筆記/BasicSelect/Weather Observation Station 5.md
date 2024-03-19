# Weather Observation Station 5
> https://www.hackerrank.com/challenges/weather-observation-station-5/problem?isFullScreen=true  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/2c416861-1e80-4213-af0f-fbcacfe0e07b)
### 題目意思
> 搜尋程式名，字母數最小的城市 與 字母數最多的城市，如果出現重複，就選出排列的第一筆作為答案
> 舉例 :
```
有 4 個城市 : DEF, ABC, PQRS and WXY.
排序後變成  : ABC、DEF、PQRS 和 WXY
最長的為 PQRS
而最短的 ABC、DEF、 WXY 選 ABC 第一順位作為查詢結果
```
> 可以透過兩個搜尋來找出結果
### MYSQL
```
SELECT CITY, LENGTH(CITY) FROM STATION
ORDER BY LENGTH(CITY), CITY
LIMIT 1;

SELECT CITY, LENGTH(CITY) FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY
LIMIT 1;
```
