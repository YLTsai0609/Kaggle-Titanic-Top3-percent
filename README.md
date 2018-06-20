# Introdution

[Kaggle](https://www.kaggle.com)為一個培育資料科學家全世界性競賽平台，企業以及研究者可在其上發布數據，統據學者及數據挖掘專家可在其上進行競賽已產生最好的模型，其中[Titanic](https://www.kaggle.com/c/titanic)為該平台上的一個入門競賽，為一個小資料集的二元分類比賽，本專案使用RandomForest作為測試模型，並以Recursive Forward Elimination(RFE)前向選擇法執行特徵選擇，使用5個特徵(性別，艙等，票價，連結，年齡)將預測排名從全世界11487個隊伍中的達到第301名(Top 3%)，分成兩個版本，英文版內含一個ipynb文件，中文版內含一篇Medium文章以及一個ipynb文件:

## English 

[Recursive Forward Elimination Workflow to 0.82296](https://github.com/YLTsai0609/Kaggle-Titanic-Top3-percent/blob/master/Recursive%20Forward%20Elimination%20Workflow%20to%200.82296.ipynb)


## Chinese 

[The post on Medium](https://medium.com/@yulongtsai/https-medium-com-yulongtsai-titanic-top3-8e64741cc11f)

[The Code](https://github.com/YLTsai0609/Kaggle-Titanic-Top3-percent/blob/master/Titanic%20Top%203%25%20on%20Medium.ipynb)


# Missing Data Problem
[缺失值問題](https://zh.wikipedia.org/wiki/缺失数据)為數據探勘及機器學習中資料預處理的一個常見問題，其中包含是否需要補植以及各式各樣的補植方式
，本資料集在年齡的特徵中含有約20%的缺失值，在文章[3 Strategies analyzing Age and Their Impact](https://github.com/YLTsai0609/Kaggle-Titanic-Top3-percent/blob/master/3%20Strategies%20analyzing%20Age%20and%20Their%20Impact%20.ipynb)中則討論了對於此資料集的3種補值方法以及對預測的影響。
