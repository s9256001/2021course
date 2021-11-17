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
- adversarial training: GAN (Generative Adversarial Networks)

    ![](https://user-images.githubusercontent.com/11552271/142250418-d85ff34e-d7da-4a3a-b11b-904c9ccb82a6.png)
    
    ![](https://user-images.githubusercontent.com/11552271/142250655-08c35dcb-afa2-493f-930d-89ca928f003f.png)

- iGAN
    - 朱俊彦等人 (ECCV 2016)
    - https://arxiv.org/abs/1609.03552
    - 人人都是大畫家!
    - https://youtu.be/9c4z6YsBGQ0

    ![](https://user-images.githubusercontent.com/11552271/142253494-1b4c42c7-1f0a-429b-b53b-cb1260b9d6be.png)

- Progressive GAN
    - Karras 等 NVIDIA 團隊 (ICLR 2018)
    - https://arxiv.org/abs/1710.10196
    - 生成 1024x1024 明星照片
    
    ![](https://user-images.githubusercontent.com/11552271/142253836-4ea2ea92-d788-4273-8ab6-6b2c6aa537d9.png)

- Pix2Pix
    - Isola, 朱俊彦等人 (CVPR 2017)
    - https://arxiv.org/abs/1611.07004
    - 把衛星圖變地圖
    
    ![](https://user-images.githubusercontent.com/11552271/142254106-5bec3a47-094d-4300-ab77-7c389b2a775b.png)
    
    - 隨手畫畫變街景
    
    ![](https://user-images.githubusercontent.com/11552271/142254337-07c7a6a9-66e9-4fa2-aed2-83d66f38f6af.png)

    - Pix2pix 線上版
    - https://affinelayer.com/pixsrv/
    
    ![](https://user-images.githubusercontent.com/11552271/142254686-fbcfd8af-862e-4a53-a79d-9fca70de9b1c.png)

## 6-6 GAN有趣的應用
- CycleGAN
    - 朱俊彦等人 (ICCV 2017)
    - https://arxiv.org/abs/1703.10593
    - 如男變女的照片、女變男的照片
    - 為了避免生成器總是產出同樣的照片, 透過走一個 cycle, 而要與原圖相似度很高的檢驗 (如此可以比較簡單的收集訓練集)
    
    ![](https://user-images.githubusercontent.com/11552271/142256204-1cff1b65-d0fb-4e15-accb-b245dddfd296.png)
    
    - 馬變斑馬
    - https://youtu.be/9reHvktowLY

    ![](https://user-images.githubusercontent.com/11552271/142256288-ac8afaf6-db20-44c3-adfd-5bf1c870b9f0.png)

    - 館⻑變陳沂 (魏澤人老師)
    - https://youtu.be/Fea4kZq0oFQ
    
    ![](https://user-images.githubusercontent.com/11552271/142256325-e5a908bc-119b-4743-b580-9626e20e8bc3.png)

## 6-7 CycleGAN令人驚呆的魔法
