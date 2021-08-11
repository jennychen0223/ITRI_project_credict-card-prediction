# 信用卡潛在客戶預測
## 專案介紹

1. 本專案目的為藉由分類模型訓練預測銀行對信用卡有興趣的潛在客戶，專案利用Python做資料探勘、數據分析、建立模型與效益評估。實作結果顯示，嘗試過Logistic Regression, Decision Tree Classifier, Random Forest Classifier, XGBoost, KNN等模型，最終以XGBoost模型準確率達到90.05%為最優。
2. 將最終模型利用LINE Bot串接API，部署至Heroku形成實際上可使用的平台

## 資料來源

本次資料是利用Kaggle平台釋出作為開放性議題，提供使用者建立分類模型進行預測。
（JOB-A-THON - May 2021- Credit Card Lead Prediction）

資料來源：https://www.kaggle.com/sajidhussain3/jobathon-may-2021-credit-card-lead-prediction?select=sample_submission.csv

## 專案步驟：

- 了解資料
- 資料前處理
- 資料比較
- 模型評估
- LINE Bot實現

## 了解資料

1. 訓練資料：245,725筆、11個欄位
2. 測試資料：105,312筆、10個欄位
<img width="749" alt="image" src="https://user-images.githubusercontent.com/81677812/128292795-1c32abc7-bcbd-4b3a-a69b-f5fb6cdc55a8.png">

## 資料前處理

1. 處理空值：刪除空值欄位效果較好
2. 類別型資料：利用Label Encoder轉換成數值資料
3. 數值型資料：分佈較離散，進行標準化
4. Age欄位：偏左分佈，故取Log使資料分布呈常態分佈

## 資料比較

1. 數據樣本中，因目標正、負資料比例分佈不平均，正：76.3%、負：23.7%，故採SMOTE方法在少數類樣本之間，利用差值來產生額外的樣本。
2. 利用特徵值比較，刪除關聯性較低欄位
3. 拆分訓練資料80%、測試資料20%

## 模型評估

|         模型結構          |  準確率 |
| -------------------------|--------| 
|    Logistic Regression   | 85.04% |
| Decision Tree Classifier | 86.59% |
| Random Forest Classifier | 88.93% |
|          XGBoost         | 90.05% |
|          Lightgbm        | 88.63% |
|            KNN           | 84.69% |
|            DNN           | 86.00% |

## LINE Bot實現
1. 建立聊天機器人，使用者依照機器人的指令，回傳客戶資料，最終會回傳預測結果
2. 優點：使用便利、快速回覆、可立即根據結果做相對應的處理
3. 
<img width="341" alt="image" src="https://user-images.githubusercontent.com/81677812/128297888-e221daba-e9c8-4c03-9385-032177c85b61.png">

<img width="347" alt="image" src="https://user-images.githubusercontent.com/81677812/128297963-bb8d6dc5-05b1-4990-beb9-788243c86ab3.png">



