單元 5:遞歸神經網路 RNN
=========================

## 5-1 遞歸神經網路RNN
- RNN (Recurrent Neural Network): 有記憶的神經網路
- RNN 會將上一次的輸出, 轉化為一個向量 hidden state, 當作下一次的輸入

    ![](https://user-images.githubusercontent.com/11552271/137932032-7655ffe1-dac6-4fa6-bf26-b4d91d5f8f12.png)

## 5-2 遞歸層怎麼讓神經網路有記憶？
- 遞歸層的選項:
    - 每層幾個神經元

    ![](https://user-images.githubusercontent.com/11552271/137935461-a3381bc2-4994-4263-9e30-ffdf8900ea4d.png)

- 遞歸層可以看為, 此次輸入加上上次記憶 hidden state, 形成的標準全連結神經網路

    ![](https://user-images.githubusercontent.com/11552271/137936012-a9a0f62a-2d9a-45f4-bac9-09a4bd6b8c21.png)

## 5-3 RNN最重要的應用是對話機器人
- 應用: 對話機器人

    ![](https://user-images.githubusercontent.com/11552271/139704512-b9df8e2f-732b-4ab5-974e-f8d3fd6f94f1.png)
    ![](https://user-images.githubusercontent.com/11552271/139704556-3947e519-0ac5-4cae-86db-570982470c2f.png)
    
    ![](https://user-images.githubusercontent.com/11552271/139704598-80a94a5e-8856-44b0-a1e3-8f6072558941.png)
    
## 5-4 RNN有趣的應用
- RNN 有趣的應用:
    - 自動翻譯
    - video captioning (為影片產生描述文字)
    - 生成文章
        - Andrej Karpathy 生出代數幾何介紹 "Stacks" 的文字
            - http://karpathy.github.io/2015/05/21/rnn-effectiveness/
        - 以莎士比亞的文體創作

## 5-5 RNN的訓練和罩門
- RNN 訓練的兩個問題:
	- 很難做平行處理
	- 通常是很深的神經網路, 而很難訓練
- RNN 訓練稱為 backpropagation through time (BBPT)
    
    ![](https://user-images.githubusercontent.com/11552271/139905979-6fdc6870-7606-48cd-bc68-7960e2cd98dd.png)
    
    ![](https://user-images.githubusercontent.com/11552271/139906028-6a5fda4a-1529-4c89-856a-f6da0d0f19e2.png)
    
	- gradient 乘起來的過程中, 會有梯度消失、梯度爆炸的問題

## 5-6 RNN兩大救星：LSTM、GRU 不公開
- 解決梯度消失、梯度爆炸的問題:
	- LSTM (Long Short Term Memory)
	- GRU (Gated Recurrent Unit): 可以想為 LSTM 的稍為簡化版本
- 原始的 RNN 稱為 Vanilla RNN, 在 TensorFlow 中是 SimpleRNN

## 5-7 全壘打預測的應用
- 題目: 某 MLB 選手新球季可以打幾支全壘打

	![](https://user-images.githubusercontent.com/11552271/140771110-a0724180-fbad-488c-bbb0-2417a4c181b4.png)
	
	- 輸出採用 one-hot encoding
	- 一層 LSTM 隱藏層
	- 輸出層做 softmax
	- 使用 10 年資料訓練

## 5-8【實作】讀入IMDB電影資料庫
- 由老師的 repo 建立副本:
	- [Colab] > [GitHub]
	- 搜尋 "yenlung", 找到存放區 "yenlung/Deep-Learning-Basics", 選取檔案 "03 RNN 做情意分析.ipynb"
	- [檔案] > [在雲端硬碟中儲存副本]
- [編輯] > [筆記本設定] > 選擇 [GPU]
- https://colab.research.google.com/drive/1bGDp_R680vyiKz07elNZKFsbMiwANh8Q?usp=sharing

## 5-9【實作】用RNN做情意分析

## 作業五：程式作業—用 RNN做情意分析
- https://colab.research.google.com/drive/1b2ahlEZx14KzvAjH9vwgMjGZItSbt-ie?usp=sharing
