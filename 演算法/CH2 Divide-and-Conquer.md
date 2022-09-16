---
date created: 2022-09-15 16:17
date updated: 2022-09-15 17:28
---

# Divide-and-Conquer

## 2.1 Introduction

Divide-and-Conquer 是一種演算法的策略

- Divide: 將原問題**切分**成多個子問題
- Conquer: 遞迴**解各個子問題**，子問題夠簡單就可以直接解
- Combine: 子問題**合併**成原問題

#### [Merge-Sort](Merge-Sort.md)

_**T(n)= 𝝷(n lg n)**_

## 2.2 The maximum subarray problem

==給一整數陣列A[1..n], 求其中具有最大元素和之subarray?==

### Max-Subarray

- Divide: 切成左右子陣列
- Conquer: 遞迴求出子陣列的最大子陣列
- Combine: 取左子、右子、跨越三個之中的maximum subarray

![](img/截圖%202022-09-15%20下午4.34.59.jpg)

> T(n) = 2T(n/2)+𝝷(n)
> T(1) = 𝝷(1)

_**T(n)= 𝝷(n lg n)**_

### Max-Subarray-DP

![500](img/截圖%202022-09-15%20下午4.40.30.jpg)

```txt
Max-Subarray-DP(A):
	max = A[1]
	r = A[1]
	for i =2 to n:
		if r+A[i] > A[i]: 
			r = r+A[i]
		else: 
			r = A[i]
		if r > max:
			max = r
	return max
```

## 2.3 Matrix multiplication

使用Divide-and-Conquer
切成4個大小為`n/2*n/2` 的矩陣
![500](img/截圖%202022-09-15%20下午4.54.49.jpg)

> 但效果不會比暴力法好，都是𝝷(n^3)

### Strassen's method

![300x400](img/截圖%202022-09-15%20下午4.54.57.jpg)

> T(n) = 7T(n/2)+𝝷(n²)
> T(1) = 𝝷(1)

_**T(n) = 𝝷(n^lg7) = 𝝷(n^(2.81))**_

## 2.4 The selection problem

==給訂n個相異數，求第k小的數==
使用[Merge-Sort](Merge-Sort.md)然後取第k位數=>O(n lg n)

#### [Prune-and-search](Prune-and-search.md)

### The selection algorithm

1. 將input分成upper(n/5)堆
2. 每組做sorting
3. 求出P(中位數中的中位數)
4. 找出P為第幾小
5. 求S1, S2。(S1是<p的、S2是>p的)
6. 分析。假設p為第x小的數
   1. x = k, return p 。 ==找到了==
   2. x < k, 去掉左上，求剩餘第 k - |S1|小
   3. x > k, 去掉右下，求剩餘第 k 小

![500](img/截圖%202022-09-15%20下午5.27.47.jpg)

> T(n) = T(n/5)+T(3n/4)+O(n)

_**T(n) = O(n)**_

`NOTE:若改成4個一堆則時間超過O(n)`
