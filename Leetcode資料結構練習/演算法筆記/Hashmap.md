# Hashmap 觀念
> * HashMap 是一個用於儲存 Key-Value 的集合，每一個 ```鍵(key)``` 都對應一個 ```值(Value)```。
> * 每一個 ```鍵值對``` 也叫做 ```Entry```，每個 Entry 分散儲存在一個數組當中
> HashMap 如下
![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/0c3e41a3-6810-44b4-ab34-b8cd8b08c0d3)

## Hashmap index(索引值長度)
> HashMap 的初始默認 index 長度都是 16， index 由 0 ~ 15

## 發生碰撞
> HashMap 有時候再添加新的 Key-Value 時，會發生碰撞的情況，也就是不同鍵值計算出相同的 HashCode，然後放置在同樣的 ```index 位置```。然而 Hash map 大小是有限制的  
> 因此發生碰撞的時候，最常見的方式就是 ```拉鍊法(Chaining)```，使用 鏈結串列 ```(linker list)``` 或是 ```紅黑樹（Red-Black Tree）```把發生碰撞新的 Key-Value 存放到對應的位置。
> > * ```鏈結串列 (linker list)``` : 這個方法就是把 發生碰撞```新的 Key-Value``` 存放到對應的```桶子裡下一個位置```，不過缺點就是```鍊表太長```可能降低搜尋時的速度，因此還可以使用 ```紅黑樹（Red-Black Tree）```改善。這個方法的時間複雜度為 ```O(n)```， n 為列表長度
> > * ```紅黑樹（Red-Black Tree）``` : 在 Java 8 中，Linker list 長度超過 8 的時候，會將鍊表轉換成紅黑數，紅黑樹可以參考 [5] 。這個方法的時間複雜度為 O(log n) n 為列表長度
### 鏈結串列 (linker list) 與 紅黑樹（Red-Black Tree） 時間複雜度  
> 簡單來說，假設今天有一個列表長度為 32 ，來分析一下兩種方法的搜尋時間  
> > ```1.鏈結串列 :``` 時間複雜度就是 ```O(32)```，最壞情況下要走 32 步才能找到想要的目標元素  
> > ```2.紅黑樹（Red-Black Tree） :``` 時間複雜度就是 ```O(log 32)```，底數為2的對數函數的話，就是 2 的 5 次方，所以這種方式最壞也只需要走 5 步就可以找到目標元素  
> > 所以當列表長度越長，鏈結串列方式所需花費的時間就會比紅黑數來的更長  
#### 參考資料:
[1] https://jianjiesun.medium.com/python%E7%AD%86%E8%A8%98-8-hashmap-%E9%9B%9C%E6%B9%8A%E8%A1%A8-697f4baa650a  
[2] https://segmentfault.com/a/1190000039774584
[3] https://www.twblogs.net/a/61dd1e2105d76fbd5d59955f
[4] https://ithelp.ithome.com.tw/articles/10219279
[5] https://clu.gitbook.io/data-structure-note/1.4.3-red-black-tree
