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
	- 如下面的例子, 越滿足特徵的, 特徵強度越高:
	
	![](https://user-images.githubusercontent.com/11552271/137013163-849ade7a-5550-4385-b0b8-d21dc061bf80.png)
	![](https://user-images.githubusercontent.com/11552271/137013194-6ff90caa-96f7-4629-949a-5215ad0db319.png)

## 4-5 其實神經元的動作和以前一樣
