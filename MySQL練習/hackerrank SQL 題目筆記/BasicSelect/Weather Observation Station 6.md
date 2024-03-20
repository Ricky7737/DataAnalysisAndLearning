# Weather Observation Station 6
> https://www.hackerrank.com/challenges/weather-observation-station-6/problem  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/3f13e94f-bec3-4030-9d77-f6469d855465)
### 題目意思
> 查詢城市欄位開頭為 ``a e i o u``` 城市名稱，然後同時排除重複的資料
### MYSQL
```
SELECT DISTINCT CITY
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU]';
```
### 語法筆記
> REGXP 為一種正規表達式，REGXP 相關請參考以下筆記連結 :
> https://github.com/Ricky7737/DataAnalysisAndLearning/new/main/MySQL%E7%B7%B4%E7%BF%92/hackerrank%20SQL%20%E9%A1%8C%E7%9B%AE%E7%AD%86%E8%A8%98/SQL%20%E8%AA%9E%E6%B3%95%E7%AD%86%E8%A8%98
