# SELECT DISTINCT
> 在 SQL 中，```SELECT DISTINCT``` 用來查詢 ```目標欄位中不重複的值```，通常與 ```SELECT```  一起使用

* 舉例
```
table name: Name
  -------------------
  |   name         |
  -------------------
  |   John         |
  |   Jane         |
  |   John         |
  |   Smith        |
  |   Jane         |
  -------------------
```
> select distinct name from Name
```
---------------
|   name      |
---------------
|   John      |
|   Jane      |
|   Smith     |
---------------
```
