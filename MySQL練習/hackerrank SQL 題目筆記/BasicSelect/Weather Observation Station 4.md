# Weather Observation Station 4
> https://www.hackerrank.com/challenges/weather-observation-station-4/problem?isFullScreen=true  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/d9a14c1f-c8a1-4980-b419-10842765bfec)
### 題目意思
> 求 STATION 表單中，CITY 欄位資料總數 與 不重複的CITY資料列數相差多少
> 舉一個例子
```
table name:STATION
CITY 裡有三列資料 : 'New York', 'New York', 'Bengalaru'
不重複的只有 'New York', 'Bengalaru'
3 - 2 = 1
```
### MYSQL
```
select count(CITY) - count(distinct(CITY)) from STATION;
```
