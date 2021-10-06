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

