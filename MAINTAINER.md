# methodology-kit — 维护者备忘（Owner）

> **读者**：工具包维护者（本人），非面向一般同事。对外入口请只指向 **[README.md](./README.md)**。

**不知道 GitHub 仓库该包含哪些路径时**，先看 **[REPO_SCOPE.md](./REPO_SCOPE.md)**（公开 `methodology-kit` + 私有整库、同事协作、**`archive/`** 归档说明）。

工作区根目录已提供 **`../README.md`**（私有库总览）。**`archive/`** 仅本机、不进入 Git，说明见 **`../archive/README.md`**。

---

## 落地路线图（建议顺序）

### Phase A — 本周可完成（几乎不依赖他人）

| # | 动作 | 产出 |
|---|------|------|
| A1 | 把本目录 **推到你控制的 Git 仓库**（公开或私有） | 可引用 URL、Issue/PR、Release |
| A2 | 用 `CODEBOOK_TEMPLATE.md` 填一版 **Stream 2 真实 codebook 摘要**（可脱敏） | 同事看到的「金标准」 |
| A3 | 在 `decisions/` 里用 `ADR_TEMPLATE.md` 写 **2～3 条**已发生的真实决策（如 E/C 边界、Stream1A 与 S2 差异） | 决策可追溯 |
| A4 | 新项目先填 `domain_adaptation_intake.md` | 领域迁移不拍脑袋 |

### Phase B — 1～2 周内（需整理素材）

| # | 动作 | 产出 |
|---|------|------|
| B1 | 从 `skills/` 复制 Skill 草稿到本机 `~/.cursor/skills/`（或 Claude 等价目录），按需改触发语 | AI 辅助闸门与 E/C 辨析 |
| B2 | 在仓库开 `examples/`：放一个 **匿名化** 的 QEC JSON 片段 +「错误 E/C」对照 | 培训材料 |
| B3 | 可选：GitHub Pages / Cloudflare Pages 渲染本目录（仅 MD） | 非开发同事只读 |

### Phase C — 持续迭代

| # | 动作 | 产出 |
|---|------|------|
| C1 | 每踩一个坑 → 一条 ADR + 必要时更新 `E_vs_C.md` | 方法论版本化 |
| C2 | 与 `stream2-analysis/docs/`、`stream1a/docs/` **互链**（项目文档指向 methodology-kit 的 release tag） | 防止两套说法漂移 |

---

## 仓库里已就绪 vs 仍需你动手

### 已就绪（可直接给同事用）

- `CODEBOOK_TEMPLATE.md`、`E_vs_C.md`、`ADR_TEMPLATE.md`、`domain_adaptation_intake.md`  
- `skills/` 下 Skill 草稿  

### 必须由你或团队完成

- 注册 Git 远程、推送、权限与脱敏策略  
- 把真实 codebook 摘录进模板  
- 内部合规：能否公开、公开到什么程度  

### 可继续在 AI 会话里做的

- 根据真实 QEC 写 `examples/` 正例 / 反例（脱敏后）  
- 在 `stream1a/README.md` 等增加指向 `methodology-kit/README.md` 的链接  
- 调整 Skill 触发语为团队常用说法  

---

## 版本建议

对外发布或写论文时，打 **Git tag**（例如 `methodology-kit/v0.1.0`），正文引用固定 tag，避免日后文档改了却找不到当时版本。

---

## 与对外 README 的分工

| 文件 | 用途 |
|------|------|
| **README.md** | 给**拿到工具包的同事**：是什么、怎么用、文件索引 |
| **MAINTAINER.md** | 给**你自己**：怎么发布、排期、维护清单 |
