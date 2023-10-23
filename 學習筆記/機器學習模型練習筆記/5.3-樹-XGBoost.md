# XGBoost（eXtreme Gradient Boosting）
* 參考網址 : https://ithelp.ithome.com.tw/articles/10273094
#### XGBoost 採用隨機採樣的方式與隨機森林方法一樣生成多棵簡單的決策樹(Decision Tree)。但這會使模型可能過於複雜化，而噪音也會隨之增加影響模型判斷能力，所以 XGBoost 結合正則化使損失函數更加平滑。
* XGBoost 圖片。參考連結 : https://machinelearningmastery.com/visualize-gradient-boosting-decision-trees-xgboost-python/
* ![image](https://github.com/Ricky7737/DataAnalysisAndLearning/assets/58324475/f48388ec-e99b-4c63-927e-a9add9b0c270)

## 1. XGBoost 優點
   * **1.高準確性**，而且可以自動處理數據分布不平衡的能力
   * **2.自動處理遺漏值**，無須另外處裡
   * **3.自動分配重點特徵權重**
   * **4.因為引入正則化方式**，所以可以防止模型過度擬合，更如意泛化的未來的測試數據
   * **5.支援自動停止訓練機制** : 當數據訓練到一定程度無法在提升時，則會啟動停止訓練機制防止模型過度擬合
   * **6.提升梯度(Gradient)** : 梯度為 **"預測值"與"實際值"** 之間的誤差

## 2. XGBoost 參數介紹
   * **1.n_estimators :** 決策樹數量，也稱迭代次數，每次迭代都會建立新的決策樹
   * **2.max_depth:** 控制每顆決策樹的最大深度，深度越深模型可能越複雜，也容易出現過度擬和
   * **3.learning_rate:** 學習速度，控制每一次迭代參數更新的幅度，較小的學習速率可以使模型收斂較穩定，但可能需要更多的迭代次數
   * 其他的可以參考這裡 : https://blog.csdn.net/m0_37870649/article/details/82707197

以下待會再補充程式片段
