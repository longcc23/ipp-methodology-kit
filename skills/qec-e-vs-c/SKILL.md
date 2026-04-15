---
name: qec-e-vs-c
description: >
  在 QEC（Quote–Explanation–Code）编码时辨析 E 与 C：避免把解释写进 Code、或让
  Explanation 沦为重复原文。用于「编码审校」「新人培训」「和同事对齐标签」。
  触发：E和C分不清、QEC审校、Explanation怎么写、Code定义。
---

# QEC：E 与 C 辨析

## 何时调用

- 审校一批 QEC JSON/表格，怀疑 E、C 边界混乱  
- 新同事第一次写 Explanation  
- 合并 codebook 前做一致性检查  

## 执行步骤

1. 打开项目中的方法论母本：`methodology-kit/E_vs_C.md`（或与该文档同版本的副本）。  
2. 对每条有争议的 QEC，依次问：  
   - **删掉 Q 后，E 是否仍是一句完整主张？** 若否，重写 E。  
   - **C 是否能在 codebook 中唯一对应？** 若否，改 C 或拆 Q。  
3. 仍无法达成一致 → 要求记录 **ADR**（使用 `methodology-kit/ADR_TEMPLATE.md`），不要口头定论。

## 禁止

- 用 C 字段写长句解释  
- E 与 C 字面完全同义而不增加信息  

## 输出格式建议

对每条问题编码，给出三行：**原 QEC 摘要 → 问题类型 → 修改建议**。
