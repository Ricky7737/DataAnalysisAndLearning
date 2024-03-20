# Weather Observation Station 8
> https://www.hackerrank.com/challenges/weather-observation-station-8/submissions/code/375378869  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/6bcfbe6f-8d09-4aa3-bf98-a41bfb7c2e85)

### 題目意思
> 找出城市名稱字母 ```開頭``` 與 ```結為``` 為  ```a e i o u``` 的城市
### MYSQL
```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU].*[aeiouAEIOU]$';
```
