# Weather Observation Station 10
> https://www.hackerrank.com/challenges/weather-observation-station-10/problem?isFullScreen=true
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/53e55993-d6a7-48c5-b40f-928b4b867ac3)
### 題目意思
> 找出城市名稱結尾字母不為 a e i o u 的城市名稱
### MYSQL
```
SELECT DISTINCT CITY 
FROM STATION
WHERE CITY NOT REGEXP '[aeiou]$';
```
