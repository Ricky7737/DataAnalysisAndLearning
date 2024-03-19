# Weather Observation Station 3
> https://www.hackerrank.com/challenges/weather-observation-station-3/problem?isFullScreen=true  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/f9854892-0646-4913-8d9e-04d6e6ee8c0b)
### 題目意思
> 搜尋 ID 為偶數的城市名稱，並且排序
### MYSQL
```
select distinct CITY from STATION
where MOD(ID, 2) = 0
order by CITY;
```
