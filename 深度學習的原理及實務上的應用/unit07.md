單元 7:強化學習和AI近期發展
=========================

## 7-1 強化學習震撼世界
- 強化學習 (Reinforcement Learning)
- AlphaGo

    ![](https://user-images.githubusercontent.com/11552271/142453810-48efd197-629f-4b5c-a5d9-ffdae35e2562.png)

## 7-2 兩個強化學習的方式
- 強化學習基本架構

    ![](https://user-images.githubusercontent.com/11552271/142455079-185ec761-9ee8-4300-acc4-e2eb6893bfc4.png)

- policy based
    - 很難訓練準備資料
    
    ![](https://user-images.githubusercontent.com/11552271/142455418-9cb9016e-3db8-4ea6-b82c-e093b90686d0.png)

- value based

    ![](https://user-images.githubusercontent.com/11552271/142455578-aae797a2-d19d-4a59-9219-d20e427a6c3b.png)

## 7-3 Deep-Q Learning
- greedy policy: 將動作帶入 Q 函數, 挑選得分最高的動作
    - Q: 評分函數
    - S: 環境
    - a: 動作
    
    ![](https://user-images.githubusercontent.com/11552271/142761368-19e69e03-3bed-45fb-80d9-1357a87c3c04.png)
    
- Deep Q-Learning: 用神經網路學習 Q 函數

## 7-4 訓練資料是怎麼做出來的？
- Deep Q-Learning: 給定一小部分的 Q 值, 利用深度學習的方式, 自己生訓練資料自己學
- <img src="https://render.githubusercontent.com/render/math?math=\varepsilon">-greedy policy: 由於一開始時, Q 函數還不準

    ![](https://user-images.githubusercontent.com/11552271/142762267-d85b0983-69a3-4d7d-81f8-bad106d90b86.png)

- experience replay  
    ![](https://user-images.githubusercontent.com/11552271/142762308-5a4ba7c5-d48f-4399-bc3e-c1c051636a24.png)
    ![](https://user-images.githubusercontent.com/11552271/142762326-f822b02e-59eb-4e04-80fa-05b1a2dc099f.png)
    
    ![](https://user-images.githubusercontent.com/11552271/142762363-e48455f8-04d8-4f86-ab70-065b2dc9354f.png)

## 7-5 應用範例-自動交易系統
- 卷積深度 Q-學習之 ETF 自動交易系統
- 基本設定
    - 選一支 ETF
    - 開始 20000 美金
    - 經過一年全賣手上 ETF
    - 使用 Deep Q-Learning
- 狀態: 每天資料含 6 個數值為開盤價、收盤價、最高、最低、成交價...
    
    ![](https://user-images.githubusercontent.com/11552271/142896663-eb06338a-a8e0-48a1-8097-41e8dbb696b0.png)

- 交易結果
    - CDQN: Deep Q-Learning
    - 無腦法: 買入持有策略
    
    ![圖片](https://user-images.githubusercontent.com/11552271/142896771-34d1cf16-e918-4a8c-b9a2-82ad9e597302.png)

- 實務上要多做幾年、還要可以挑出適用此學習得來的交易方式的股票

## 7-6-1 進擊的自然語言處理-1
