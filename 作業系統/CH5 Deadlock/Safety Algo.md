---
date created: 2022-09-14 12:46
---
# Safety Algo

### 資料結構（新增兩個）

- Work:可用資源的累計（演算中歸還的資源累計
- Finish: 紀錄已完成的process

### 步驟：

> 概括：依序拿回可以完成的process的資源，直到無法再取回。

1. 設定初始值
2. 檢查是否有process𝒾可取得Need資源然後完成。有：goto step3，沒有：goto step4
3. Finish[𝒾] = True, Work+=Need𝒾。goto step2
4. Check Finish[1..n]。皆為True->”Safe”，否則”unSafe”
