# Weather Observation Station 7
> https://www.hackerrank.com/challenges/weather-observation-station-7/problem
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/30d414e9-9d0d-4aba-834b-795b4e0fe5ca)
### 題目意思
> 找出城市名稱字母結為為  ```a e i o u``` 的城市
### MYSQL
```
SELECT DISTINCT CITY 
FROM STATION
WHERE CITY REGEXP '[aeiou]$';
```
