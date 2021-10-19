單元 3:全連結神經網路 DNN
=========================

## 3-1 上個世紀就大紅的神經網路
- Universal Approximation Theorem
	- 神經網路只要一層 hidden layer, 就能學會任何函數
- 神經網路不用知道函數的形狀 (線性、多項式)

![](https://user-images.githubusercontent.com/11552271/135728780-f511ec4e-84e8-4e0c-87a7-f217d5be458a.png)

## 3-2 神經網路的寒冬
- 之前神經網路遇到的困難
	- 複雜的軟體
	- 電腦計算能力
	- 大量的數據
- 重大論文
	- "Mastering the game of Go with deep neural networks and tree search"
	- "Human-level control through deep reinforcement learning"
- Deep Learning 三巨頭的故事
	- http://bit.ly/ai_history

## 3-3 DNN的基本架構
- DNN: Full Connected Neural Network, 1980 年代火紅的 model
	- 層層之間的神經元是完全連結
	- 選項: 幾層 hidden layer、每層幾個神經元

	![](https://user-images.githubusercontent.com/11552271/136219900-b025b4ad-de9c-463f-a719-ff92fa6d12b5.png)

- 深度學習: 早先指三層以上的神經網路 (新世紀的潮流), 但現在又泛指所有以神經網路設計的機器學習
  	- 選項: 決定 hidden layer 的類型
		- DNN: 全連結層 (Dense)
		- CNN: 卷積層 (Conv)
		- RNN: 遞歸層 (LSTM、GRU)

## 3-4 神經元的運算方式
- 神經元的運作
	- 接受多個不同權重 (表示重要性) 的輸入, 產出一個輸出
	- 權重、偏值需要經過學習得到
	
	![](https://user-images.githubusercontent.com/11552271/136230587-9d03abc9-23cf-438e-b066-87fb129598b6.png)

- 總刺激
	
	![](https://user-images.githubusercontent.com/11552271/136229935-cca2f519-3593-44c7-bc9c-f0584799e580.png)

- 偏值 (bias)

	![](https://user-images.githubusercontent.com/11552271/136230054-b1391a77-0fbf-4aed-831f-294ee627be92.png)
	
- 透過激發函數 (activation function) 轉為非線性

	![](https://user-images.githubusercontent.com/11552271/136230336-ade90ffa-d49b-47f8-94ac-3d94e811c1db.png)

- 激發函數
	- Gaussian: 早期使用, 現在已很少使用
	- Sigmoid: 類似 s 型, 接近生物神經元的動作
	- ReLU: 由兩個線性函數組成, 現在很常用
	
	![](https://user-images.githubusercontent.com/11552271/136230187-9223e506-d873-4225-ae40-388b33f36086.png)

## 3-5 練習：假裝自己是一個神經元
- 學習的權重、偏值合起來稱為 theta

	![](https://user-images.githubusercontent.com/11552271/136437093-0f349d3e-1e08-44f2-8a0c-a61c57a21a81.png)

- 一開始隨機給初始值, 輸出公式如下

	![](https://user-images.githubusercontent.com/11552271/136437169-2fcfb73d-928c-442a-ae74-6fec87e6f2c3.png)

## 3-6 損失函數是訓練神經網路的標準
- 神經網路透過作訓練資料學習, 學習法叫 backpropagation (反向傳播: 評估學習參數)
- 每個 theta 決定一個函數, 目標是要找出最好的 theta*, 使得與目標函數最接近
- 利用 loss function 計算訓練資料的輸出與正確答案的差異, 然後調整參數
- 常見的 loss function mean square error (MSE) 如下 (前面的 1/2 是為了微分的計算化簡):

	![](https://user-images.githubusercontent.com/11552271/136439214-7ff021b2-101f-4c52-9b91-182fcc540fef.png)

- 每次的參數調整方式如下:

	![](https://user-images.githubusercontent.com/11552271/136439268-4355c6de-3975-497d-ab56-edcfca86d66a.png)

## 3-7 神經網路的學習方式
- 先假設只有一個參數
	- 要最小化 loss function, 要往與斜率相反的方向調整
	
	![](https://user-images.githubusercontent.com/11552271/136609204-c3c5c711-0377-4143-a623-6b8bc4c013d8.png)
	
	- 為了避免步伐太大, 不容易收斂的問題, 斜率再乘上 learning rate
	
	![](https://user-images.githubusercontent.com/11552271/136609360-99e502d3-0e99-4aa7-8594-e4687d93746c.png)

- gradient descent
	- 多參數的情況, 使用偏微分, 將各參數的斜率以一個梯度 (gradient) 向量表示

	![](https://user-images.githubusercontent.com/11552271/136609668-b1a08c24-b93d-4d83-bbed-5b9c3ed58e3f.png)
	![](https://user-images.githubusercontent.com/11552271/136609714-df4fac08-a05f-4b6f-80a8-e3e61f8c14f2.png)

	- 深度學習使用 gradient descent 訓練神經網路

## 3-8 實作手寫辨識
- python 的神經網路套件:
	- TensorFlow: google
	- pytorch: facebook
- MNIST (Modified NIST (美國國家標準暨技術研究院)): 手寫數字辨識的數據集
	- 輸入是 28*28 的灰階圖, 輸出是數字

	![](https://user-images.githubusercontent.com/11552271/136610893-70b2b149-3884-415a-aaf0-3d1f7d92a1ea.png)

	- 輸出使用 one-hot encoding, 再透過 softmax 轉為機率
	
	![](https://user-images.githubusercontent.com/11552271/136611227-4d202dbb-49b9-49e1-96f0-eb5006285ffa.png)

	- DNN 輸入必須是向量, 此處使用 784 (=28*28) 維的向量
	
	![](https://user-images.githubusercontent.com/11552271/136611138-c6c2d656-2bdf-42b2-8404-65f1b9af4f86.png)

## 3-9【實作】讀入MNIST訓練資料
- 由老師的 repo 建立副本:
	- [Colab] > [GitHub]
	- 搜尋 "yenlung", 找到存放區 "yenlung/Deep-Learning-Basics", 選取檔案 "01 標準的 Fully Connected (Dense) NN.ipynb"
	- [檔案] > [在雲端硬碟中儲存副本]
- [編輯] > [筆記本設定] > 選擇 [GPU]
- tensorflow 主流寫法是用 keras, keras 是 goolge 出的另一個套件
- https://colab.research.google.com/drive/16Sa9HlszHRVGXfhS_49mhkhMGtPOBqBg?usp=sharing

## 3-10【實作】用DNN做手寫辨識
