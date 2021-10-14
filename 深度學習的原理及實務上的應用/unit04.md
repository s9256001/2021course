單元 4:卷積神經網路 CNN
=========================

## 4-1 圖形辨識的天王CNN
- CNN (Convolutional Neural Networks): 適用於圖形辨識, 非全連結

## 4-2 CNN是救了神經網路的大功臣
- CNN 經典作品 (Tensorflow 都可以使用)
	- InceptionV3
	- VGG16/VGG19
	- ResNet50

## 4-3 CNN的兩種隱藏層之卷積層
- CNN 有兩種隱藏層:
	- 卷積層 (convolutional layer)
	- 池化層 (pooling layer)
- 卷積層的選項:
	- 幾個 filter
	- 每個 filter 的大小 (如 3x3)
- filter 卷積的運算
	- filter 由左上掃描像素點到右下, 紀錄該點附近的特徵強度, 每個 filter 紀錄不同的特徵

	![](https://user-images.githubusercontent.com/11552271/137012451-fce9e019-fec5-4cc4-9852-aecd534b8079.png)

	- filter 會與 input 同大小的一個區塊做 component-wise 乘法, 然後把值加起來作為特徵強度; 也會搭配偏值、激發函數, 類似神經元的機制

	![](https://user-images.githubusercontent.com/11552271/137012131-73215cf5-0b2b-41b2-99a9-e57e1ab5941a.png)

	![](https://user-images.githubusercontent.com/11552271/137012228-3eb561d1-e36e-487d-960d-e38dd8c8018f.png)
	![](https://user-images.githubusercontent.com/11552271/137012250-5e35db16-8281-4b70-b905-b9d64d664ebf.png)

## 4-4 為什麼卷積會抽取特徵？
- 如下面的例子, 越滿足特徵的, 特徵強度越高

	![](https://user-images.githubusercontent.com/11552271/137013163-849ade7a-5550-4385-b0b8-d21dc061bf80.png)
	![](https://user-images.githubusercontent.com/11552271/137013194-6ff90caa-96f7-4629-949a-5215ad0db319.png)

## 4-5 其實神經元的動作和以前一樣
- 可以將圖上的每一個點視為輸入層神經元, 每一個計算出的特徵強度也視為一個神經元, 則卷積層可以視為不完全連結的神經網路, 只是每組連結共享同一組權重 (filter)
	
	![](https://user-images.githubusercontent.com/11552271/137182714-f5902af7-99da-45c9-b034-9e66de98a551.png)
	![](https://user-images.githubusercontent.com/11552271/137182745-8054d0ad-3506-4aa6-bb4d-937f2994d284.png)

## 4-6 我們希望記分板和原圖一樣大
- 前述的方式, 邊緣的線段會掃描不到
	
	![](https://user-images.githubusercontent.com/11552271/137183807-81ea1754-2f50-4edd-a668-b05e8e511fef.png)
	
- 我們喜歡把外圈加 0, 如此可以掃到邊緣, 但輸出的特徵強度會跟原圖一樣大

	![](https://user-images.githubusercontent.com/11552271/137183836-4795b21f-9e09-4775-bbaf-cc666e57406e.png)
	
- 衍生出的問題是, 今天如果有 10 個 filter, 數據量會變 10 倍

## 4-7 CNN的兩種隱藏層之池化層
- 池化層 (pooling layer): 決定區域的特徵強度
- 池化層的選項:
	- 池化區域大小 (如 2x2)
	- 池化方式 (如取極大值 (max-pooling layer))
	
	![](https://user-images.githubusercontent.com/11552271/137366204-c1faa108-ed22-4c6b-a65a-3e1f83ca8a9f.png)

## 4-8 常見的CNN設計架構
- 設計架構
	- 基本圖形特徵 > 組合基本特徵 > 複合特徵 > ... > 拉平一堆矩陣 (對應每一個 filter) 到 Dense
	- Conv filter 數量通常會越來越多 (組合數比較多) (如 16 > 32 > 64)
	
	![](https://user-images.githubusercontent.com/11552271/137367175-0b2407be-9621-4924-b557-95bd21041727.png)

## 4-9【實作】用CNN做手寫辨識
