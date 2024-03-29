# Boyer–Moore majority vote algorithm(摩爾投票算法)
> 這個演算法用於 => 如何在不知道多少元素的陣列中，找出最多數出現的那個，透過不斷消除不同元素間的對抗，最終留下來的就是多數元素。
> * 舉一個簡單的例子:  假設班級投票選出班長
>   * A 有 10 票  
>   * B 有 5 票  
>   * C 有 3 票  
>     
> 根據 ```摩爾投票原則``` A當選  

### 使用情境  
> 1.找出陣列中出現在次數超過一半的元素。適用投票系統  
> 2.找出數據中的眾數  

### 使用限制  
> 1.找尋元素必須存在陣列中    
> 2.無法找出多個主要元素    
> 3.無法得知最多次出現元素，具體出現的數量    

### 時間複雜度 與 空間複雜度
> ```時間複雜度```: O(n)，n 為陣列長度，透過迴圈將陣列元素跑過一次而已  
> ```空間複雜度```: O(1)，該投票法使用固定的變數，不會隨著輸入大小變化  
> 
## 摩爾投票演算法邏輯
> 假設有一個陣列名稱為 nums  
> 演算法開始時，先設置一個 ```候選元素 candidate``` 與一個 ```計數器 count```，初始設定皆為 0  
> for 迴圈開始遍歷 nums陣列 中每一個元素  
> > * 1.如果 count = 0，表示沒有候選元素，將 候選元素設定為 nums 第一個陣列， 將 count 設定為1 表示這個數出現一次
> > * 2.如果 下一個元素等於上一個元素， count 繼續 +1 。如果 下一個元素不等於上一個元素，count -1   
>
>反覆進行步驟 2 剩下的 candidate 為最終答案

### 演算法程式(Python3)
```
def majorityElement(nums):
    candidate = 0 #設定初始候選變數
    count = 0     #初始計數變數為 0

    # 設定投票來選出元素
    for num in nums:
        # 如果 count表示計數歸 0，就要把候選設定成下一個元素
        if count == 0:       #如果計數次數為0
            candidate = num  #設定第一個候選變數為陣列第一個元素

        # 設定好元素後直接開始比對 
        if num == condidate: # 如果 候選元素 = 陣列中指定到的元素
            count += 1       # 計數 +1
        else:                # 如果 候選元素 != 陣列中指定到的元素
            count -= 1       # 計數 -1
    return cadidate  # 回傳最終的候選元素  
```

### 舉例一個陣列來顯示邏輯
> 假設我們有一個陣列 nums = [2,2,3,2,1]
```
input = [2,2,3,2,1]
1.初始值
candidate = 0 
count = 0  

1.
[2,2,3,2,1]
 ^
當前元素為2，count = 0，candidate = 2， 所以 count+1 = 1。
把初始候選設定的元素設定為 2，2號 1票
----------------------------
[2,2,3,2,1]
   ^
count = 1，candidate = 2， 等與 nums =2，所以 count 1+1 = 2
此時 2 號又出現一次，與候選元素相同，所以 2 號多增加一票
----------------------------
[2,2,3,2,1]
     ^
count = 2,candidate = 2, 不等於 nums =3，count 2-1 = 1
接下來 出現3號，與候選元素 2 號不同，透過自我抵銷，也就是 3 號抵銷一票，2號同時也抵消一票
----------------------------
[2,2,3,2,1]
       ^
count = 1,candidate = 2, 等於 nums = 2, count 1+1 = 2
再來 2 號再次出現一次，一樣2號加一票，所以 2 號目前獲得 2 票
----------------------------
[2,2,3,2,1]
         ^
count = 2,candidate = 2, 等於 nums = 1, count 2-1 = 1
此時出現 1 號，跟候選 2 號不一樣，透過 1 號自我抵銷，2號票數也抵消一票剩下 1 票

nums 完整跑完一次結束迴圈
最終剩下的為 2 號
```
#### 再舉一個例子來算
```
nums = [1,1,0,0,3,3,3,2,2,2,2,4]
初始值
c = 0 (計數器變數)
m = 0 (候選變數)

進入 for 迴圈，每一次 for 迴圈 num 會去個別存取 nums 陣列第1個元素到最後一個元素
1.nums = 1
[1,1,0,0,3,3,3,2,2,2,2,4]
 ^
第一個 if 後, c = 0, m = 1
在下一個 if num = 1 == m = 1, c +1 = 1
--------------------------------------------------------
2.num = 1
[1,1,0,0,3,3,3,2,2,2,2,4]
   ^
直接進入第二個 if, num = 1 == m = 1, c + 1 = 2
--------------------------------------------------------
3.num = 0
[1,1,0,0,3,3,3,2,2,2,2,4]
     ^
此時 num = 0 != m = 1, 進入下面else c - 1 = 1
--------------------------------------------------------
4.num = 0
[1,1,0,0,3,3,3,2,2,2,2,4]
       ^
此時 num = 0 != m = 1, 進入下面else c - 1 = 0
--------------------------------------------------------
5.num = 3
[1,1,0,0,3,3,3,2,2,2,2,4]
         ^
c = 0, 進入第一個 if 這時候 m 變成 3
進入第二個 if, num = 3 == m = 3, c + 1 = 1
--------------------------------------------------------
6.num = 3
[1,1,0,0,3,3,3,2,2,2,2,4]
           ^
c = 0, 進入第一個 if 這時候 m 變成 3
進入第二個 if, num = 3 == m = 3, c + 1 = 1
--------------------------------------------------------
7.num = 3
[1,1,0,0,3,3,3,2,2,2,2,4]
             ^
進入第二個 if, num = 3 == m = 3, c + 1 = 2
--------------------------------------------------------
8.num = 2
[1,1,0,0,3,3,3,2,2,2,2,4]
               ^
進入第二個 if, 因為 num = 2 != m = 3 , 所以else c - 1 = 2
--------------------------------------------------------
9.num = 2
[1,1,0,0,3,3,3,2,2,2,2,4]
                 ^
進入第二個 if, 因為 num = 2 != m = 3 , 所以else c - 1 = 1
--------------------------------------------------------
10.num = 2
[1,1,0,0,3,3,3,2,2,2,2,4]
                   ^
進入第二個 if, 因為 num = 2 != m = 3 , 所以else c - 1 = 0
--------------------------------------------------------
11.num = 2
[1,1,0,0,3,3,3,2,2,2,2,4]
                     ^
此時 c = 0, 進入第一個 if, m = nums = 2
然後再進入下一個 if, nums = 2 == m = 2, c + 1 = 1
--------------------------------------------------------
12.num = 4
[1,1,0,0,3,3,3,2,2,2,2,4]
                       ^
進入第二個 if, 因為 num = 4 != m = 2 , 所以else c - 1 = 0

for 迴圈已經完全跑過一次 nums 陣列
回傳最後的 m = 2
所以這時候最多數為 2
```

#### 參考資料 :  
[1] https://ithelp.ithome.com.tw/articles/10213285  
[2] https://cloud.tencent.com/developer/article/1600607  
[3] https://vocus.cc/article/652ca296fd897800019bfe1f
