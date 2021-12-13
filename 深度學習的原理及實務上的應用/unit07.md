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
- word embedding: 將字 (詞) 產出特徵向量的函數
    
    ![](https://user-images.githubusercontent.com/11552271/142899236-909b605b-c26e-437a-bfe0-d3e9e725384a.png)

- 輸入也要編碼: 可以用字出現頻率排序, 越常出現給的編號越小

    ![](https://user-images.githubusercontent.com/11552271/142899588-cb89121b-d9e4-4571-834b-ca129c9c70a9.png)

    - 要破除連續的關聯, 採用 one-hot encoding

        ![](https://user-images.githubusercontent.com/11552271/142899643-e4a2d0f3-c01a-40e7-8ea0-747f1d26385c.png)

- Word2Vec: 一種 word embedding, 相似的字會在一起

    ![](https://user-images.githubusercontent.com/11552271/142899864-281e21a1-ad44-4367-89e5-601394ab1726.png)
    ![](https://user-images.githubusercontent.com/11552271/142899942-a07cfda9-550d-4adb-b7de-d00268f54ba1.png)

    - 設計一個任務, 這個任務需要電腦懂字的意思才能做到
    - CBOW model: 用周圍的字預測中間的字
    
        ![](https://user-images.githubusercontent.com/11552271/142900236-aa5b425c-acbc-478b-bda8-665112654df1.png)

    - Skip-Gram model: 用中間的字預測周圍的字
    
        ![](https://user-images.githubusercontent.com/11552271/142900280-2b207953-9201-4565-9d80-43797646f1bd.png)
    
    - 由中間隱藏層的神經元表示特徵向量
    
        ![](https://user-images.githubusercontent.com/11552271/142900495-4949804f-5246-4c10-9db5-d04c8fa6f7ff.png)

- 傳統 word embedding 的缺點: 每個字 (詞) 有固定的特徵向量, 但一個字 (詞) 可能再不同的地方有不一樣的意思
- ELMo: 用意涵來編碼
    
    ![](https://user-images.githubusercontent.com/11552271/142900780-dace7158-3a69-4f4a-b105-4753f3b263fa.png)
    
    - RNN 的 hidden state 可以做 embedding
    
        ![](https://user-images.githubusercontent.com/11552271/142900949-af741706-2874-4f5a-8a73-079fce4e13eb.png)
    
    - 可以做兩層, 第二層表示更深層的意涵
    
        ![](https://user-images.githubusercontent.com/11552271/142901050-f40d3692-2373-44b9-9f3c-3c95ac77df89.png)
    
    - word embedding 為三個值加權計算
    
        ![](https://user-images.githubusercontent.com/11552271/142901229-61a73f48-1f8e-4cf7-935a-4b71aa2539f9.png)

## 7-6-2 進擊的自然語言處理-2
- Attention Model: 生出關注的每個字的比重可能不一樣
    
    ![](https://user-images.githubusercontent.com/11552271/143279717-4c9b773e-9339-46ff-946f-8a82b088b7c1.png)

- Transformer: 可看為第四種神經網路; 運用 self-attention, 避開 RNN 要一個字一個字輸入的缺點
- BERT: 使用 transformer 的 encoder, 其中一種訓練方式是克漏字

    ![](https://user-images.githubusercontent.com/11552271/143279794-aef10099-5508-416b-a0ef-b70fdff22f7c.png)

- GPT: 唬爛王
    - https://talktotransformer.com/

## 7-7 學習怎麼學習的meta learning
- meta learning: 用少資料, 學習如何學習
    
    ![](https://user-images.githubusercontent.com/11552271/143282261-3f003cb2-ab70-4e1c-a039-797775e0dd75.png)

- 範例: 人臉辨識
    
    ![](https://user-images.githubusercontent.com/11552271/143282482-39075f42-a719-41fe-a47a-bb362c3479ab.png)
    ![](https://user-images.githubusercontent.com/11552271/143282508-d9a0341a-0883-4d13-a6b0-6e7c623ead0e.png)

- 想法: 抽取特徵向量

    ![](https://user-images.githubusercontent.com/11552271/143282796-5a4b15ba-8b56-4aa0-af49-ff67618526a9.png)
    ![](https://user-images.githubusercontent.com/11552271/143282858-c2ccb5b9-11f5-4529-849b-dcaba4d2d491.png)

- 訓練方式

    ![](https://user-images.githubusercontent.com/11552271/143282978-ca525316-f85c-496a-8251-df49990360e9.png)
    
    ![](https://user-images.githubusercontent.com/11552271/143283009-12f9d5b7-953c-475b-b296-0af5102249ea.png)
    
    ![](https://user-images.githubusercontent.com/11552271/143283038-a5aa2ff6-da24-4621-b128-9a207347f4a2.png)

## 作業七：發想作業—強化學習和AI近期發展
1. AI應用：德州撲克AI
2. 輸入：目前的手牌、公牌
3. 解決問題的函數：依目前的手牌、公牌, 判斷效益最大的動作
4. 輸出：效益最大的動作
5. 資料來源與數量：採用 Deep Q-Learning, 使用人工規則初始 Q 值, 後續讓電腦自己生訓練資料自己學
