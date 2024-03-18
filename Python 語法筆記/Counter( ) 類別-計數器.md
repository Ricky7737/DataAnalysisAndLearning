# Python - Counter( ) 類別
> * ```Python Counter()``` 是用來快速計算 list 中每個元素出現的次數。  
> * 可以透過快速迭代物件中的元素，產生一個 字典
> * 以下舉一個例子 :
```
程式碼 :
from collections import Counter
my_list_count = Counter(my_list)
print(my_list_count)

Input : my_list = [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]
output : Counter({1: 2, 2: 2, 3: 2, 4: 2, 5: 2})
```
