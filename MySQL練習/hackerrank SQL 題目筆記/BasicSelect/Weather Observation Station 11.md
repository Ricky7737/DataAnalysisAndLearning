# Weather Observation Station 11
> https://www.hackerrank.com/challenges/weather-observation-station-11/problem?isFullScreen=true
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/3887d238-a7f9-43e6-a86c-30d4dfa80709)

### 題目意思
> 找出城市名稱字母 ```開頭``` 與 ```結為``` 不為  ```a e i o u``` 的城市
### MYSQL
```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT REGEXP '^[aeiouAEIOU].*[aeiouAEIOU]$';
```
