---
date created: 2022-09-14 12:37
---

# Ch5 Dead lock

- ## 例子：四個十字路口
- ## 四個必要條件
    1. #### [Mutual exclusion](Mutual%20exclusion.md)
    2. #### [Hold and wait](Hold%20and%20wait.md)
    1. #### [No preemption](No%20preemption.md)
    1. #### [Circular waiting](Circular%20waiting.md)
- ## 與starvation比較(Deadlock/Starvation)
| 情況        | Deadlock                    | Starvation                   |
| ----------- | --------------------------- | ---------------------------- |
| 1. 定義     | 沒有機會完成                | 有機會完工只是機會渺茫       |
| 2. 發生條件 | 4個條件                     | 發生在不公平環境＆可搶奪環境 |
| 3. 影響      | 產能下降                    | 無                           |
| 4. 解決方法    | prevention, Avoidance, etc… | Aging                        |
|             |                             |                              |
- ## Deadlock
	> 定義：系統中存在一組processes彼此行程circular waiting 情況，造成陷入死結之processes皆無法往下執行，使得Throughput, utilization不良之結果。

     - RAG 資源配置圖(Resource Allocation Graph)
    	三點結論
		- *No cycle => No deadlock*
		- *有cycle =?> 有deadlock* 
		- *每種Resources皆為單一數量，有cycle => 有deadlock**

- ## Deadlock 處理方法
	- ### Prevention
    > 破除四項條件
    1. #### 破除mutual exclusion
       > 辦不到！！！
    2. #### 破除hold&wait
       *作法一*：process要一次取得所有所需的資源，否則無法取得
       *作法二*：可取得部份資源，但要取得其他資源時，要將先前的資源全部歸還。
    3. #### 破除No preemption
       (Easy)改為preemption
    4. #### 破除Circular waiting
       Resource ordering
	- ### Avoidance
	    - [Safe state](Safe%20state.md)
	    - [Unsafe state](Unsafe%20state.md)
	    - #### [Banker Algorithm](Banker%20Algorithm.md)
	- ### Detection
	    1. [Deadlock Free](Deadlock%20Free.md)
	    2. 若每種res.都只有一個->可用RAG「簡化」
				  - claim edge: “P𝒾- - - - >R𝒾”:代表P𝒾未來會對R𝒾申請資源
				  - 過程（4 steps）
					  1. Check 對應的chaim是否存在
					  2. Check 申請的R𝒾是否avaialble（是：goto 3./否：等待）
					  3. 試算：claim edge 改成 Allocation
					  4. 執行Safe Algo. （有cycle:否決/沒cycle:核准）
	      1. 若每種res.都只有一個->可用RAG「簡化」-> 使用Wait-For Graph
		      **Wait-For Graph**
		      >移掉res.，變成P1等待P2的關係圖(有circle就有deadlock)
	- ### Recovery

      1. Process 在deadlock時終止
		      - （法ㄧ）終止所有process: [cost高]過去的成果全白費
		      - （法二）一次中止一個process直到deadlock cycle消失：[cost高]需不斷執行[Detection Algo.](Detection%20Algo..md)
      2. [Resource Preemption](Resource%20Preemption.md)
		    > 缺：cost 高，注意starvation 
