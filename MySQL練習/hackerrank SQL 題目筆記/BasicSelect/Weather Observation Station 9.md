# Weather Observation Station 9
> https://www.hackerrank.com/challenges/weather-observation-station-9/problem?isFullScreen=true  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/f6dcdc92-0904-4f4e-96fa-700a1ba22c6a)

### 題目意思
> 找出城市名稱字母 ```開頭```  不是為  ```a e i o u``` 的城市
### MYSQL
```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT REGEXP '^[aeiouAEIOU]'
```
