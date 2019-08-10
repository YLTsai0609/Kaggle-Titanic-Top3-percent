# Kaggle-Titanic-Survival-prediction
[Kaggle-Titanic-Survival-prediction](https://www.kaggle.com/c/titanic)<br>
E-mail : [yltsai0609@gmail.com](yltsai0609@gmail.com) <br>
**********************************************
結論 : Titanic為機器學習的入門款項目，Kaggle上有許多解法及思路，
然而沒有一篇使用較少的特徵達到較好的效果，多半使用大量的調參技巧，
少量，有品質的特徵提供穩定的預測品質，快速的訓練及預測，<br>
你可以在這裡找到使用前項選擇法來做特徵選擇的Kernel: 
* [Recursive Forward Elimination Workflow to 0.82296](https://github.com/YLTsai0609/Kaggle-Titanic-Top3-percent/blob/master/Recursive%20Forward%20Elimination%20Workflow%20to%200.82296.ipynb)<br>
關於中文版的建模思路可以在這篇Medium文章找到:
[The post on Medium](https://medium.com/@yulongtsai/https-medium-com-yulongtsai-titanic-top3-8e64741cc11f)<br>
**********************************************
<b>以下會針對缺失值填補的方式，特徵工程及涉及的encoding方式進行說明</b>

### 缺失職填補
年齡(Age)為一項重要的特徵，由於本資料集的特性，老弱婦孺優先下船，使得年齡和和年齡高能夠有較高的存活機率，針對缺失值，我們採用的方法為使用姓名稱謂中位數進行填補

|稱謂|中位數|
|----|---|
|Mr|29|
|Rare|47|
|Master|4|
|Miss|22|
|Mrs|36|

根據EDA的結果，在一二艙等中我們發現小於16歲年齡的乘客有較高的存活率，
因此我們拿16歲當作切分值

|特徵|值|
|---|--|
|age < 16|1|
|age > 16|0|

### 特徵工程

|特徵|處理方式|動機|
|----|------|---|
|Age|Binning，使用16為閥值|根據EDA的結果，在一二艙等中我們發現小於16歲年齡的乘客有較高的存活率，且binning可以有效的降低overfitting|
|Sex|直接使用|高預測性特徵，男性多半幫助女性逃生，符合直覺|
|Pclass|直接使用|乘客的社會地位，艙等越高存活率越高，符合直覺|
|Fare|Binning，按照分位數切分成4, 5, 6份比較結果|船票價格越高表示其社會地位越高，並且binning可以有效的降低overfitting|
|SibSp, Partch, Name|建立Family_size特徵，以及Connected-Survival特徵|連結在一起的家人從EDA中發現多半有一起存活或是一起為存活的現象，亦為一種Target Encoding|


## 3種缺失職填補的策略比較
[3 Strategies analyzing Age and Their Impact](https://github.com/YLTsai0609/Kaggle-Titanic-Top3-percent/blob/master/3%20Strategies%20analyzing%20Age%20and%20Their%20Impact%20.ipynb)
