---
date created: 2022-09-14 10:52
---

# AlgoCode之效能分析

- ## Space Requirement(Comlexity) Analysis

  > 定義：令sp(p)代表space requirement of Algo. P, 則sp(p) = [Fixed space](Fixed%20space.md) ＋ [Variable space](Variable%20space.md)。

  - ### 例題:
    #### Q:
    假設
    int 佔2byte,
    float 佔4byte,
    address 佔2byte,
    且list[]採用call-by-address傳遞。
    **求此code之sp(i) = ?**
    ```C
    float rsum(float list[], int n){
    	if(n!= 0)
    		return rsum(list, n-1)+ list[n-1];
    	return list[0];
    }
    ```
    #### ANS: **6*n bytes**
    1. 先決定_每發生一次resursion 要push多少data 大小_到stack
       參數值：list[], n (2 + 2)。區域變數值： 無。反回位址：必定需要(2) => **6 byte**
    2. _共發生幾次遞迴_
       => **n次**（不含進入時的那次）

- ## Time Requirement(Comlexity) Analysis
  > 定義：令T(p)代表Algo./Code: P之Time需求，則_T(p) = Development Time + Execution Time_。本課程旨care "exec. Time"
  - ### 如何評量Algo./Code之exec. Time?
    1. #### Measurement方法
    2. #### [Analysis(or 預估)方法](Analysis(or%20預估)方法.md)
