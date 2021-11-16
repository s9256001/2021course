單元 1:人工智慧與深度學習的概念
=========================

## 0 課程說明
### 評分方式
- 期中考、期末考 (線上) 30% (可做多次)
- 作業 (7 次) 70%
### Colab
- 線上工具, Google 帳號登入, 免費使用 GPU、TPU (張量處理單元)
### 資源
- "少年Py的大冒險：成為Python數據分析達人的第一門課"
- 鴻海的 "人工智慧導論"
- Youtube 頻道 "珊蒂微AI"

## 1-1 AI要做的事就是預測
- 通用人工智慧 (Artificial General Intelligence): human level intelligence (如哆啦A夢)
- AI 的本質是 prediction

## 1-2 三種AI之古典AI
- 廣義的人工智慧泛指自動化的行為
- 深度學習是機器學習的一個分支

![](https://user-images.githubusercontent.com/11552271/134938074-c70f9f8e-8076-4e3d-abe6-be6236660c64.png)

- 人工智慧: 資料 -> 函數 -> 預測
- AI 的目標是要學習、打造函數
- 古典 AI: 函數演算法是由專家決定的

## 1-3 三種AI之機器學習
- 傳統機器學習: feature engineering (找出資料特徵、降維 (dimension reduction))

## 1-4 三種AI之深度學習
- 深度學習: 輸入大量資料, 用神經網路去訓練 (電腦自己去抓特徵)

![](https://user-images.githubusercontent.com/11552271/135101113-8b8ff4d1-a519-4550-b60a-2eed915511f2.png)

## 1-5 AI實作就是打造函數學習機
### 神經網路 (Neural Network) 的三種模式
- DNN: 標準型、全連結 (Dense) 神經網路
- CNN: 卷積 (Convolutional) 神經網路, 適用於圖形辨識
- RNN: 遞迴 (Recurrent) 神經網路, 有記憶的神經網路
	
## 1-6 AI實作六部曲之問個好問題
### 先問一個問題
### 把問題化為函數的形式
- 輸入、輸出為 tensor
	- 純量: 0 階 tensor
	- 向量: 1 階 tensor
	- 矩陣: 2 階 tensor
- 如看照片辨識動物
	- 輸入可以是 RGB 矩陣
	
	![](https://user-images.githubusercontent.com/11552271/135106315-984b1b0f-109f-454b-b568-a13ac3f5e095.png)
	
	- 輸出可以是自定義編號 (但有數字連續性的問題)
	
	![](https://user-images.githubusercontent.com/11552271/135106441-9db1709e-e401-4d42-9942-4bd404d9214f.png)
	
	- 分類常用 one-hot encoding, 向量每一個元素標示一種動物, 數字越大代表越有可能是此類動物, 可以透過 softmax 轉換為機率
	
	![](https://user-images.githubusercontent.com/11552271/135106524-5fab05a1-bbbb-4923-8b27-ac03926698d9.png)
	![](https://user-images.githubusercontent.com/11552271/135106653-7e2ea3dc-27bd-4155-9798-50cd3fb893c3.png)
### 準備訓練資料
- 訓練資料
- 測試資料 (避免 over-fitting)
### 打造函數學習機
### 訓練學習
### 預測

## 1-7【實作】Colab的基本操作
- [新增筆記本]
- [輸入格] 可以打程式碼, shift + enter 執行
- [+文字]: 打入說明文字, 支援 Markdown、LaTex
- [工具] > [設定] > [編輯器]: 取消勾選 [自動觸發程式碼完成功能]
- [工具] > [設定] > [其他]: 好玩的效果
- ctrl + S: 儲存在 Google drive 裡面的 Colab Notebooks 內

## 1-8【實作】用Colab畫函數圖形
- https://colab.research.google.com/drive/1SMcEC5IAihjkAjqyBZ-lbX-YE9EMRxs4?usp=sharing

## 作業一：程式作業—畫個函數圖形吧!
- https://colab.research.google.com/drive/1p1sX8EdWFyMSdL2WvHsEhFdUt-L1PKRc?usp=sharing
