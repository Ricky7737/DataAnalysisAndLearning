# LinkerList(鏈結串列)
> 鏈結串列(LinkerList) 的每一個元素都成為 ```節點(Node)```，每個節點都包含 ```資料(Data)``` 與 ```指針(Pointer)```，而 LinkerList 的結尾會指向一個特定終止標記 ```Null or None```  
####  Linkerlist 結構如下 :
> ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/e48474b9-27da-473c-b520-7a63ee5a8fe7)
> 圖片來源 : https://pse.is/5qflaa
>
## LinkerList 與 Array
### Array
> * Array 是由相同型態的元素構成，而且可以快速搜尋
> * 具有固定的大小，可以預先知道需要分配多少記憶體
> * 可以利用 ```索引 index ``` 來計算 或 操作 對應位置的元素
> * 可以有 ```一維``` 或是 ```多維```構成
### LinkerList
> * 元素藉由 Node(節點) 來儲放資料，然後每一個節點都有指針指向下一個節點
> * 使用的 記憶體空間並非連續的，所以可以快速```插入```或是```取出```

### 比較
> * 存取效率 : Array 較高，因可以透過```索引(index)``` 來操作對應元素，而 LinkerList 需要一個一個往下訪問才能找到目標元素
> * 插入 或 刪除 速度 : LinkerList比較快，因為每一個 Node 都是獨立的一個存取空間，不須移動元素
> * 空間使用 : Array 需要固定空間，LinkerList 可以動態調整
> * 隨機訪問 : Array 比較快，可以透過 ```索引(index)``` 快速找到對應元素
