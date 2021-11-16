單元 6:生成模式和生成對抗網路
=========================

## 6-1 為什麼要討論生成模式呢？
- 圖靈測試: 是否可以區分機器與人

## 6-2 生成模式兩個基本作法
- 生成模式 (generative model)

    ![](https://user-images.githubusercontent.com/11552271/141142715-0c304c62-a3ad-4c4e-ada9-c978e1b78386.png)

- 特徵向量有兩種做法
    - 方法一: 隨機輸入一堆數字
    
    ![](https://user-images.githubusercontent.com/11552271/141143843-6092484a-3a1e-49a1-86a1-fc4d59797401.png)
    
    - 方法二: 學習產出特徵向量

    ![](https://user-images.githubusercontent.com/11552271/141143881-732075e6-111a-4fad-8b77-418ccba20eec.png)

## 6-3 AutoEncoder
- Autoencoder (自編碼器): 學習特徵向量, 可還原回原資料
    
    ![](https://user-images.githubusercontent.com/11552271/142020691-79015a4a-dc53-46d1-9662-6e4ea22f2b9f.png)
    
- 兩個距離很近的 laten vector, 生出來的東西卻不一定有關係

## 6-4 VAE讓我們特徵向量神奇符合常態分布
- VAE (Variational AutoEncoder): 讓 laten vector 符合常態分布
    
    ![](https://user-images.githubusercontent.com/11552271/142021764-8ce835d8-8f14-4d3c-a4c7-12ca558e3963.png)
    ![](https://user-images.githubusercontent.com/11552271/142021813-b586af15-c13b-44d4-9360-aec2f8c5057c.png)

## 6-5 很會創作的生成對抗網路GAN
