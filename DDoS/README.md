# DDoS
- DoS/DDoS掌握與實作

### 時間
- 9月16日(四) PM 19：00 DoS/DDoS掌握與實作-L1
- 9月23日(四) PM 19：00 DoS/DDoS掌握與實作-L2
- 9月30日(四) PM 19：00 DoS/DDoS掌握與實作-L3

### 投影片
- https://docs.google.com/presentation/d/1xet4rgGdSwxUBS_0mTuT7DhVka5R2MVVEHwdowNc8yg
	- backup: https://docs.google.com/presentation/d/1c5woCNvslKUzBzNe3n2WiR1oxTH5KBSfyxuBSrC2fJQ/edit?usp=sharing
- https://docs.google.com/presentation/d/1M4sLCGoo3TvBB-nzaJjHq99pwWYxvBLihb0OC6QzgM8/
	- backup: https://docs.google.com/presentation/d/1ARhwm_CXS7Qe5AzRCj0qzILw89sCI69R0SyXJPcQ9xs/edit?usp=sharing
- https://docs.google.com/presentation/d/1LH_Jqlzl6MmkRaTVOGrKGKAo7h1rSQbX_0gVmwvv9-w/edit?usp=sharing
	- backup: https://docs.google.com/presentation/d/1EeSGETfYdExi7tSxcdfaCXuJclbJM-3qnSzlLj7GxrE/edit?usp=sharing

### 環境
- virtualbox
    - https://www.virtualbox.org/wiki/Downloads
- kali
    - https://www.kali.org/get-kali/#kali-platforms
    - https://www.linuxfordevices.com/tutorials/kali-linux/install-kali-linux-on-virtualbox
- bittorrent
    - https://www.bittorrent.com/zh-tw/downloads/complete/

### L1 筆記
- 殭屍網路
    - C&C (Command and Control) Server
    - 肉雞
- 攻擊手法
    - tcp 握手握一半
    - udp 帶大封包 (佔頻寬)
    - ping 很多次, 大量壓資源
    - http 搶票, c10k (同時連線數) 問題
    - CC (Challenge Collapsar): 一個人透過代理送 (Distributed HTTP flood)
    - dns: 如讓它找不到 domain
    - Slowloris: 要監控慢速攻擊, 要看每秒服務數是否過低
- 攻擊類型
    - 頻寬攻擊型: udp flood
    - 協定攻擊型: tcp 不回應握手
    - 應用層攻擊型: http
- 防禦
    - 完整性: 被竄改, 用 hash 來檢查
    - 防禦只能緩解
    - 清洗、防禦節點, 防火牆
    - js challenge: 有通過測驗才是正常
        - challenge, captcha 只對人有用
    - 分析 request 資訊, reffer 為搜尋頁面的參考 (尋找特徵)
        - hot-link protection (防盜鏈)

### L2 筆記
- udp
    - 用在視訊
    - udp flood 帶大封包 (佔頻寬, router 要切割), 或帶小封包 (解析要資源)
- QSnatch
    - 控制 qnap (nas 系統)
    - 以往拔掉 C&C server 為一個解法, 但 QSnatch 使用域名產生演算法, 可以不停的更改域名

### L3 筆記
- 反射、放大
    - 反射可以隱藏肉機, 放大可以加大流量
    - monlist: 查看 NTP 伺服器的連線狀況, 要求最近連線的主機列表
    - 放大攻擊還是要以頻寬攻擊型來分類
- HTTP Flood 測試
    - jmeter
        - TestPlan > Add > Threads (Users) > Thread Group
            - Number of Threads (users): 500
            - Loop Count: 1
        - Add > Sampler > Http Request
            - Server Name or IP: 172.17.0.2
            - Port Number: 80
            - Path: /
    - 有些服務器會針對 4xx、5xx 的錯誤狀態碼快取, 要作隨機 request
- hping3
    - --rand-source: 提供偽造 ip 的功能
    - -c 1000: count
    - -d 80: packet size
    - -S: sync
- CC Attack: 透過跳板攻擊
    - CCATK: 用外網跳板
        - Host/Ip: niceadmin.serveblog.net
        - Page: /widgets.html
        - Port: 80
    - 講者自架服務在 gcp 上提供測試
        - Kibana: niceadmin.serveblog.net: