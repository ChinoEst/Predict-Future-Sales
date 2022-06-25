ID: P76101657  
Email:a27689259@gmail.com          kaggle: https://www.kaggle.com/chinoest

# introduction

利用以往的每日銷售數據組成的時間序列資料集，訓練一個模型，用以預測下個月每種商品和商店的銷售量。


# Data Observations 
![image](https://user-images.githubusercontent.com/92312732/175765172-32f04877-531f-42b2-a9a8-102c89563cef.png)
outline

![image](https://user-images.githubusercontent.com/92312732/175765221-b972bcbe-ff62-497a-9635-f786ec84b570.png)

# Data Preprocessing 

商品名按字母順序排列->相同系列的商品會被放在一起(用fuzzywuzzy比較相似度進行分類)

每個店名前都會有城市名->可以以城市名作分類作為features

類別名稱裡包含子類別的名稱->可以以子分類對商品進行分類作為features

在test data中，總共有363個新項目->新推出商品，無過去數據，推測銷量應該0為多數，將training data中每月賣出商品極低的設為0，讓training data和test data較為相近


# Feature selection

每月銷售總額/平均/低標/高標

每個商店、每個城市、每個類別.....等。

每月第一天和最後一天/未銷售的商品

每個商品第一次銷售與下一次的間隔時間

每個城市/商店/類別有多少新品上市

移動平均

趨勢(lag)

# Use Model

XGBoost https://zh.wikipedia.org/wiki/XGBoost


lightGBM https://en.wikipedia.org/wiki/LightGBM


# Try and Error

without any lag, with 1 lag, with all lag

del some importance features

only reserve importance features
