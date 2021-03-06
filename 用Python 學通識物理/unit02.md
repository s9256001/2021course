單元 2:我會用 Python 算速度
=========================

## 本週簡介

## 運動學簡介
- 運動學: 描述物體的運動 (位置如何隨時間演進而改變)
    - 速度 = 位移/時間
    - 加速度 = 速度變化/時間
    - 位移 = 速度 vs 時間圖的面積
    
    ![](https://user-images.githubusercontent.com/11552271/146234282-1290b201-1490-49f9-8853-e4e5250e596b.png)

## 程式規劃

## 變數與基本運算
- //: 除法結果的商
- **: 次方
- 轉型
    ```py
    a = 1
    b = '23'
    print(str(a) + b)
    # 輸出:
    # 123
    ```

## 基本輸出入
- 輸入
    ```py
    a=input('input a=')
    ```
- 輸出
    ```py
    A=16
    C=1.2955
    print(A,C)
    print('A=%7d' % A)
    print('C=%6.2f' % C)
    print('LALA',end='') # end='' 表示不換行
    print('LULU')
    # 輸出:
    # 16 1.2955
    # A=     16
    # C=  1.30
    # LALALULU
    ```

## Python 工具介紹：數列與range 函數
- list:
    ```py
    // python 為動態型別
    x=[1,'A',3]
    ```
- range
    ```py
    A = range(5)
    print('A=',list(A))

    B = range(-3,6)
    print('B=',list(B))

    C = range(1,11,2)
    print('C=',list(C))
    // 輸出:
    // A= [0, 1, 2, 3, 4]
    // B= [-3, -2, -1, 0, 1, 2, 3, 4, 5]
    // C= [1, 3, 5, 7, 9]
    ```
    
## Python 工具介紹：for 迴圈
- for
    ```py
    for i in range(5):
      print('i=',i,end='') // end='' 表示不換行
    // 輸出:
    // i= 0i= 1i= 2i= 3i= 4
    ```
    ```py
    for i in range(1,11):
	  for j in range(1,i+1):
		print('*',end='')
	  print('')
    // 輸出:
    // *
    // **
    // ***
    // ****
    // *****
    // ******
    // *******
    // ********
    // *********
    // **********
    ```

## 範例程式說明
