---
date created: 2022-09-14 12:40
date updated: 2022-09-14 12:45
---
# Banker Algorithm
`若process被否決，則等待一段時間再申請`
## 資料結構

- Request𝒾：P𝒾提出的資源申請量
- Allocation：各個process正在持有的資源量
- MAX：process全部（從頭到底）所需的資源量
- Need：process還需要的資源量 -> Need = MAX-Allocation
- Available：目前可取得的資源量

## 過程（4 steps)

1. Check Request𝒾 <= Need𝒾 ?
   > （思路：只需要10$卻申請100$?
2. Check Request𝒾 <= Available ?
   > 有充足的資源
3. 計算取得資源後的成果
   > 暫時性分配資源
4. [Safety Algo](Safety%20Algo.md).

## 時間複雜度：**O(n²*m)**

## 例題

![](img/banker_Q.jpg)

