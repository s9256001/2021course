# RabbitMQ
- RabbitMQ佇列系統

### 時間
- 8月19日(四) PM 19：00 RabbitMQ佇列系統-L1
- 8月26日(四) PM 19：00 RabbitMQ佇列系統-L2
- 9月2日(四) PM 19：00 RabbitMQ佇列系統-L3
- 9月9日(四) PM 19：00 RabbitMQ佇列系統-L4

### 投影片
- https://reurl.cc/zeV0rN
    - backup: https://docs.google.com/presentation/d/15-PMxgTBp6Y5y_WFellM9nBfNztM68ycvKjUHc4d6A0/edit?usp=sharing

### RabbitMQ admin
- url
    - http://127.0.0.1:15672
    - guest/guest
- 操作
    - 新增 exchange
        - [Exchanges] tab > [Add a new exchange]
            - Type: exchange 類型
    - 新增 queue
        - [Queues] tab > [Add a new queue]
    - 設定 exchange 與 queue 的 binding
        - [Exchanges] tab > 進入某個 exchange 編輯頁 > [Add binding from this exchange]
        - [Queues] tab > 進入某個 queue 編輯頁 > [Add binding to this queue]
            - To queue: queue 名稱
            - Routing key
    - 發送訊息
        - [Exchanges] tab > 進入某個 exchange 編輯頁 > [Publish message]
            - Routing key
            - Payload
    - 接收訊息
        - [Queues] tab > 進入某個 queue 編輯頁 > [Get messages]
            - Ack Mode: Automatic ack

### 筆記
- exchange type
    - Topic: 模糊 routing
    - Headers: 表頭
- 注單資料避免重送、漏掉的意外, 都必須稽核
- ack
    - 從 queue 抓下來後, 通常處理完才 ack, 不論多久 (除非連線斷) 都會等 ack
    - 若 consumer 發生問題已寫入但沒有 ack, 需自己利用 db 的交易性判斷是否重複寫入
