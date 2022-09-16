---
date created: 2022-09-14 10:52
---

# CH1演算法

## [[Algo定義]]
## Recursion遞迴
### 解決問題的Algo.通常有兩種
1. Recursion
2. Non-Recursion
### Recursion分類
1. Direct recursion：Algo/Code中含有自我呼叫敘述存在
2. Indirect：多個模組/副程式之間彼此行程_calling cycle_
3. Tail：是_Direct recursion之一種_，Recursion結束後之下一個執行敘述是_END_敘述
#### 比較表
|                           | Recursion | Iteration        |
| ------------------------- | --------- | ---------------- |
| **程式碼**                   | 較精簡       | 長                |
| **區域變數使用量**               | **少**     | 必定**有**，使用量**多** |
| 表達能力                      | 強大        | 弱                |
| **執行時間**                  | 久         | 較短、較快            |
| **Stack 支援**              | 需要        | 無需               |
| 執行時期空間需求                  | 較大        | 小                |
| Debug                     | 困難        | 容易               |
| `Note：Stack基本認知（副程式呼叫處理）` |           |                  
## Recursion考型與來源
### 考型
1. 給問題，write Recursive Algo/Code
2. 給Algo/Code，求追蹤其執行結果、呼叫次數、功能、複雜度
### 來源
1.  [[數學類]]
2.  未來章節
3.  其他
	1.  [[Towers of Hanoi]]
	2.  [[Permutation]] (排列組合)

## AlgoCode之效能分析
### Space Requirement(Comlexity) Analysis

  > 定義：令sp(p)代表space requirement of Algo. P, 則sp(p) = [Fixed space](Fixed%20space.md) ＋ [Variable space](Variable%20space.md)。

  - #### 例題:
    ##### Q:
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
    ##### ANS: **6*n bytes**
    1. 先決定_每發生一次resursion 要push多少data 大小_到stack
       參數值：list[], n (2 + 2)。區域變數值： 無。反回位址：必定需要(2) => **6 byte**
    2. _共發生幾次遞迴_
       => **n次**（不含進入時的那次）

### Time Requirement(Comlexity) Analysis
  > 定義：令T(p)代表Algo./Code: P之Time需求，則_T(p) = Development Time + Execution Time_。本課程旨care "exec. Time"
  - #### 如何評量Algo./Code之exec. Time?
    1. #### Measurement方法
    2. #### [Analysis(or 預估)方法](Analysis(or%20預估)方法.md)

## Space Requirement(Comlexity) Analysis

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

## Time Requirement(Comlexity) Analysis
  > 定義：令T(p)代表Algo./Code: P之Time需求，則T(p) = Development Time + Execution Time_。本課程旨care "exec. Time"
  - ### 如何評量Algo./Code之exec. Time?
    1. #### Measurement方法
    2. #### [Analysis(or 預估)方法](Analysis(or%20預估)方法.md)
## 研究所之Time Complexity 執行次數或Time Complexity
[算行數例題](算行數例題.md)
## 漸進式符號
~~去看演算法第一章~~
>目的：表達數學（時間）函數的*成長速率*之*等級*
### 符號
- 𝝤(Big-oh)
- 𝝮(omega)
- 𝝝(Theta)
- 𝝾(little-oh)
- 𝞈(little-omega)
