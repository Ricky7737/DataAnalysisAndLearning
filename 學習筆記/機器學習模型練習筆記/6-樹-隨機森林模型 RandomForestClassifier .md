# 隨機森林模型 RandomForestClassifier 
#### 基本原理就是將多個【弱學習器】組合成一個強大的模型
* ```Random Forest``` 透過多棵 ```CART樹(以 Gini 值算法的決策樹)``` 組合而成，加入資料隨機分布訓練，以增加最終模型預測準度。

## 1. 隨機森林優點
  * 1.適用於 ```分類``` 或 ```回歸```
  * 2.降低模型過度擬合，並且可以降低數據噪聲帶來的影響，魯棒性較強
  * 3.自帶處理 ```遺漏值``` 功能

##### *魯棒性 :* 意思為面對各種【不確定性】或【干擾】時，模型能夠維持 "穩定性" 和 "正常運作" 

## 2.隨機森林如何生成多棵具有差異性的樹
#### 以下分別介紹 【Bagging(Bootstrap Aggregation)】 與 【Boosting】
### 2.1 Bagging(Bootstrap Aggregation)
   * 1.透過抽取原先的資料然後生成新的資料，取樣過程皆為均勻而且可以重複抽樣
   * 2.抽取後的資料訓練出 K 個分類器(Tree)。
   * 3.抽取後的資料再放回母體重複使用
   * 4.最後每個分類器透過權重計算出最終的結果
     
### 2.2 Boosting
   * 與 Bagging 類似，但差異在於會將舊分類器錯誤的資料權重拉高，然後再訓練出新的分類器

#### 參考資料
* [1] : https://medium.com/chung-yi/ml%E5%85%A5%E9%96%80-%E5%8D%81%E4%B8%83-%E9%9A%A8%E6%A9%9F%E6%A3%AE%E6%9E%97-random-forest-6afc24871857
* [2] : https://www.nvidia.cn/glossary/data-science/random-forest/
* [3] : https://medium.com/ai%E5%8F%8D%E6%96%97%E5%9F%8E/learning-model-random-forest-ca4e3f8a63d3
