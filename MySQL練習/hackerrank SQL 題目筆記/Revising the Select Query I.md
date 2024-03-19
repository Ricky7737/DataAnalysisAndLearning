# Revising the Select Query I
> https://www.hackerrank.com/challenges/revising-the-select-query/problem  
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/6f6a22c7-d4c6-4470-9aa8-edc801e87315)
### 題目意思
> 查詢所有欄位來自 CITY 表單，然後條件為 人口(populations) 大於 100000 和 CountryCode 為 'USA'
### MySQL
```
select * from CITY
where CountryCode = 'USA' and population > 100000;
```
