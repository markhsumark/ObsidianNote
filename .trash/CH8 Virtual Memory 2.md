# Ch8 Virtual Memory
- ## 主要目的及附帶好處 #⭐️
	1.  允許process size 在超過physical memory free space size 之下，仍能執行。  
    ->logical memory size 不會受到physical memory size 之限制
	1.  觀念：即是"Partial" loading process部分內容, process 即可執行(even 不載入也可執行）
	    -   早期：dynamic loading（ＯＳ無額外支持）
	    -   現代：OS提供VM特性
	2.  其他附帶好處
	    1.  若process只載入一部分即可執行  
	        ->同時間內可載入的process數量變多  
	        ->CPU utilization 相對高  
	        NOTE:Thrash 情況除外
	    2.  less I/O Time(因為量少)
- ## Demand Pageing 技術 #⭐️
- ## Page fault 之處理 #⭐️⭐️⭐️ 
- ## EMAT計算 #⭐️⭐️⭐️⭐️
- ## 影響page fault ratio 因素
- ## Page replacement及法則 #⭐️⭐️⭐️⭐️⭐️
- ## Modification(Dirty)Bit, Belady Anomaly, stack property #⭐️⭐️⭐️⭐️
- ## Frame數目分配多寡之影響 #⭐️⭐️
- ## Thrashing 及解法 #⭐️⭐️⭐️⭐️⭐️
- ## Page size 之影響 #⭐️⭐️⭐️
- ## program structure 影響 #⭐️⭐️⭐️
- ## copy-on-write技術 #⭐️⭐️⭐️
- ## TLB Reach #⭐️⭐️