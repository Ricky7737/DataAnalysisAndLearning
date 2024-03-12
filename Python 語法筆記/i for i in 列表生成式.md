# i for i in 語法
> * 這種寫法為 Python 列表生成式的一種寫法(List Comprehension)，可以快速建立新的 list  
> * 具體來說這種寫法為對```原列表```進行遍歷 與 操作後，再給予條件生成新的列表
### 具體語法結構
```
[expression for item in iterable if condition]
```
> * ```expression``` 用來決定列表中的元素是甚麼  
> * ```item``` 則是從 iterable 中遍歷出來的每個元素  
> * ```iterable``` 是一個可以迭代的對象。可以是一組列表 或 字串等。  
> * ```if condition``` 可以篩選出那些符合條件的元素，輸出在最終的列表中。  
### 範例 1
```
nums = [1, 2, 3, 4, 5]
我們要把 nums 每一個元素進行平方

程式碼 :
nums_squared = [i**2 for i in nums]

output :
squared_nums = [1, 4, 9, 16, 25]
```
### 範例 2 
> 假設有一組字串，中有英文字母、空格、符號夾雜，但我們只需要英文字串與數字
```
input : s = ['Hello, World! 123']
-----------------------------------
程式碼 :
a = [i for i in s if i.isalnum()]
print(a)
-----------------------------------
output :
['H', 'e', 'l', 'l', 'o', 'w', 'o', 'r', 'l', 'd', '1', '2', '3']
```
