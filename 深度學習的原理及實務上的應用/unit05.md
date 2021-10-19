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
