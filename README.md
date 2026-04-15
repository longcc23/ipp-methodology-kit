# IPP 研究方法论工具包

欢迎。这里是一套可复用的 **质性文本研究协议** 模板，与具体行业、具体数据集解耦。你在做访谈编码、对话分析、评价文本、工单等 **需要「可追溯的结构化单元 + 主题聚合」** 的研究时，可以按下面顺序使用本目录中的文件。

本工具包在 **GMBA IPP** 项目中与真实研究并行演进，核心方法见各 Stream 的详细文档（见文末链接）。

---

## 这套工具解决什么问题

1. **统一语言**：用 **QEC（Quote–Explanation–Code）** 把「原文证据 → 你的解释 → 可统计的标签」拆开，避免编码时混在一起。  
2. **少踩坑**：尤其是 **E（解释）和 C（代码标签）** 的分工——详见 `E_vs_C.md`。  
3. **换数据也能起步**：新数据源先填 `domain_adaptation_intake.md`，再决定编码方案和流水线。  
4. **决策留痕**：重要方法选择用 `ADR_TEMPLATE.md` 记在 `decisions/` 里，方便以后写论文、答辩或交接。

---

## 建议怎么用（第一次打开时）

| 步骤 | 做什么 |
|------|--------|
| 1 | 阅读 **[E_vs_C.md](./E_vs_C.md)**（约 10 分钟），建立 E/C 的共同标准。 |
| 2 | 若是**新领域或新数据类型**，先填 **[domain_adaptation_intake.md](./domain_adaptation_intake.md)**，再开会讨论。 |
| 3 | 复制 **[CODEBOOK_TEMPLATE.md](./CODEBOOK_TEMPLATE.md)** 为项目专用 codebook，从试点样本开始填词表。 |
| 4 | 方法上有分歧或重大变更时，在 `decisions/` 下新增一条 ADR（从 **[ADR_TEMPLATE.md](./ADR_TEMPLATE.md)** 复制）。 |

需要 **在 Cursor / Claude 里用自然语言触发辅助** 时，见 **[skills/README.md](./skills/README.md)**。

---

## 文件一览

| 文件 | 给你什么 |
|------|----------|
| [CODEBOOK_TEMPLATE.md](./CODEBOOK_TEMPLATE.md) | 编码手册骨架（QEC 定义、证据强度、Code 词条结构） |
| [E_vs_C.md](./E_vs_C.md) | Explanation 与 Code 的边界、自检句、正反面例子 |
| [ADR_TEMPLATE.md](./ADR_TEMPLATE.md) | 方法决策记录模板 |
| [domain_adaptation_intake.md](./domain_adaptation_intake.md) | 新数据源 / 新领域准入问卷 |
| [decisions/README.md](./decisions/README.md) | ADR 建议命名与存放位置 |
| [skills/](./skills/) | 可安装的 AI Skill 草稿（E/C 辨析、准入问卷、阶段闸门） |

---

## 与本仓库中案例研究的对应关系（可选读）

若你正在同一仓库里工作，可参考已跑通的方法论文档与执行说明：

| 内容 | 路径 |
|------|------|
| Stream 2（渠道访谈 · 方法论长文） | `stream2-analysis/docs/methodology_framework.md` |
| Stream 1A（AI Coach 对话 · 步骤与陷阱） | `stream1a/README.md` |
| Cross-stream（交叉验证） | `cross-stream/README.md` |

---

## 版本与引用

发布或写作若需**固定某一版方法**，请使用本仓库的 **Git tag / Release**（具体 tag 名由项目维护者公布）。正文可写：「方法协议见仓库 `methodology-kit` 目录 @ tag xxx」。

