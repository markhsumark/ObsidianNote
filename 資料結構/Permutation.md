# Permutation
  - ## Q3:Write down a Recursive Algo./Code 列應n個資料之排列組合
    > 觀念：輪流當head字元
    
    ### Code:
    ```C
	void Perm(char* A, int i, int n){
		//列印A[i]~A[n]排列組合, i<= n
		// Assume A:[1..n] of char
		if(i == n){
			for(int j = 0; j <= n; j++){
				printf("%c", A[j]);
				// 排序數量加一
			}
		}else{
			for(int j = i; j<= n ;k++){
				SWAP(A[i], A[j]);//換A[j]當頭。實練輪流當頭的「換頭」步驟
				Perm(A, i+1, n);//A[i+1:n]的排列組合
				SWAP(A[i], A[j]);//還原
			}
		}
	}
	```
	### 練習:
	A = abc, 求Perm(A, 0, 2) ***寫出輸出順序！！***
	>`abc` `acb` `bac` `bca` `cba` `cab`
	### 複雜度:
	>n個data有n!種排列組合，每列印一種花O(n) => total: O(n!*n)`