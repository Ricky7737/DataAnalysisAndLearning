# 隨機森林模型 RandomForestClassifier 
#### 基本原理就是將多個【弱學習器】組合成一個強大的模型
* ```Random Forest``` 透過多棵 ```CART樹(以 Gini 值算法的決策樹)``` 組合而成，加入資料隨機分布訓練，以增加最終模型預測準度。

## 1. 隨機森林優點
  * 1.適用於 ```分類``` 或 ```回歸```
  * 2.降低模型過度擬合，並且可以降低數據噪聲帶來的影響，魯棒性較強
  * 3.自帶處理 ```遺漏值``` 功能
  * 4.不管大樣本還是小樣本都可以使用

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

## 3.隨機森林使用環境
   * ```金融環境 :``` 透過隨機森林可以找出 "忠誠度" 較高的顧客。或是找出叫劣質的顧客
   * ```醫學環境 :``` 可以分析病患的 "醫療紀錄"，以便判斷未來病患的疾病
   * ```股票市場 :``` 可以識別股票的 "行為" 與 "預期" 的 "損失" 或 "利潤"
   * ```電子商務環境 :```透過分析過往客戶的消費行為與愛好，來預測未來的客戶是否喜歡推薦產品。

## 4.隨機森林使用於【分類 Classification】與【回歸 Regression】
   * ```分類 Classification :``` 使用多數投票法(majority voting) 下去對資料做分類，然後確定最終分類的結果
   * ```回歸 Regression :``` 隨機森林也可以用在回歸問題，差別在於這是預測一個數值結果。

## 5.隨機森林使用 IRIS 數據集練習
#### 5.1 載入套件
```
### 載入套件
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn import metrics
from sklearn import datasets
```
#### 5.2 載入資料 與 檢視資料
```
## 檢視欄位
iris = datasets.load_iris()
## 檢視目標變數
print(iris.target_names)
## 檢視特徵
print(iris.feature_names)

out:
['setosa' 'versicolor' 'virginica']
['sepal length (cm)', 'sepal width (cm)', 'petal length (cm)', 'petal width (cm)']
```
```
# 將 iris 資料轉換成 dataframe
#  columns: 將直行名稱設定為feature_names欄位，方便觀察
iris_df = pd.DataFrame(iris['data'], columns=iris['feature_names'])
# 新增 taget 欄位
iris_df['target'] = iris['target']
iris_df
```
* ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/70d8a425-ce97-4081-b0ab-04ad9bd07fe6)
#### 5.3 分割資料
```
# 切割資料
# 先刪除目標
X = iris_df.drop(['target'], axis=1)
y = iris_df['target']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3)
```
#### 5.4 建立模型
```
## 建立模型
clf = RandomForestClassifier(n_estimators=100)
clf.fit(X_train, y_train)
y_pred = clf.predict(X_test)
y_pred

out:
array([1, 2, 1, 1, 0, 2, 2, 2, 0, 0, 0, 0, 2, 2, 2, 0, 0, 1, 0, 1, 0, 1,
       1, 2, 1, 1, 2, 1, 0, 1, 1, 1, 0, 2, 2, 2, 2, 1, 0, 0, 2, 0, 2, 2,
       2])
```
#### 5.5 檢視模型分數
```
## 計算模型分書
print('Accuracy', metrics.accuracy_score(y_test, y_pred))
out:
Accuracy 0.9333333333333333
```

#### 詳細資料參考資料
* [1] : https://medium.com/chung-yi/ml%E5%85%A5%E9%96%80-%E5%8D%81%E4%B8%83-%E9%9A%A8%E6%A9%9F%E6%A3%AE%E6%9E%97-random-forest-6afc24871857
* [2] : https://www.nvidia.cn/glossary/data-science/random-forest/
* [3] : https://medium.com/ai%E5%8F%8D%E6%96%97%E5%9F%8E/learning-model-random-forest-ca4e3f8a63d3
* [4] : https://tomohiroliu22.medium.com/%E6%A9%9F%E5%99%A8%E5%AD%B8%E7%BF%92-%E5%AD%B8%E7%BF%92%E7%AD%86%E8%A8%98%E7%B3%BB%E5%88%97-37-%E9%9A%A8%E6%A9%9F%E6%A3%AE%E6%9E%97%E5%9B%9E%E6%AD%B8-random-forest-regressor-a0f7a57c06c4
