---
date created: 2022-09-14 10:53
---

# Recursion遞迴

## 解決問題的Algo.通常有兩種

1. Recursion
2. Non-Recursion

![[IMG_2193 1.heic]]

## Recursion分類

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
| `Note：Stack基本認知（副程式呼叫處理）` |           |                  |
