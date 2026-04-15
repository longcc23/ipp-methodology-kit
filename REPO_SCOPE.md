# GitHub 仓库里应该放什么（路径清单）

> 给**维护者**看的：决定「一个 Git 仓库」的边界时，按下面选一种方案即可，不必把整台电脑上的 `ipp` 文件夹原封不动传上去。

下面路径均以你本机工作区 **`ipp/`** 为根目录（即包含 `methodology-kit`、`stream1a` 等的那一层）。

---

## 先选一种策略

| 策略 | 适合什么时候 | 仓库体量 |
|------|----------------|----------|
| **A. 只发「方法论工具包」** | 主要给同事复用模板、不想暴露研究数据 | 很小 |
| **B. 发「完整研究项目」** | 要备份代码 + 文档 + 可复现分析，数据另议 | 大 |
| **C. 两个仓库** | 公开一个瘦包 + 私有一个全量 | 最清晰 |

---

## 策略 A：只上传工具包（公开给同事也安全）

**包含（整棵目录照抄即可）：**

```
methodology-kit/
```

即：`README.md`、`MAINTAINER.md`、`REPO_SCOPE.md`、`CODEBOOK_TEMPLATE.md`、`E_vs_C.md`、`ADR_TEMPLATE.md`、`domain_adaptation_intake.md`、`decisions/`、`skills/` 等**全部**在 `methodology-kit/` 下的文件。

**不要放进这个仓库的：**

- `stream1a/`、`stream2-analysis/`、`cross-stream/`（除非你有意做单体仓库，见策略 B）
- **`archive/`**（本地归档整目录，与 Git 无关）
- `.claude/`、本机配置

**GitHub 上仓库名字可以叫**：例如 `ipp-methodology-kit` 或 `qual-qec-kit`（随你）。

---

## 策略 B：一个仓库 = 整个 IPP 研究（建议 **Private**）

**建议纳入版本控制的目录：**

| 路径 | 内容 | 备注 |
|------|------|------|
| `methodology-kit/` | 工具包母本 | 与策略 A 相同 |
| `stream2-analysis/` | Stream 2 代码、文档、展示 | **数据子目录见下** |
| `stream1a/` | Stream 1A 代码、文档 | **数据子目录见下** |
| `cross-stream/` | 交叉验证 | 按实际文件 |

**强烈建议不要提交（或先脱敏再提交）：**

| 路径 / 类型 | 原因 |
|-------------|------|
| `stream1a/data/qec_final/` | 文件名含**真实姓名**；公开仓库必须排除或匿名化 |
| `stream2-analysis/data/` 下含**可识别个人**的原始访谈 | 合规与隐私 |
| **`archive/`** 整目录 | **仅本机归档**，已在 `.gitignore` 中排除，**公开/私有 Git 均不提交** |
| `.claude/settings.local.json` | 本机配置 |

**做法**：在**仓库根目录**（若仓库根 = `ipp/`，就在这里）放 `.gitignore`，例如：

```gitignore
# 本机与 IDE
.claude/
.DS_Store

# 本地归档（不进公开/私有 Git）
archive/

# 若暂不提交全量 QEC（公开库务必忽略；私有库按合规）
# stream1a/data/qec_final/
```

具体忽略哪些 `data/` 子目录，由你根据**能否公开**决定；原则是：**姓名、门店细节、未授权原文**不进公开库。**`archive/`** 按当前约定整目录忽略。

---

## 策略 C：两个 GitHub 仓库（推荐长期）

1. **`yourname/ipp-methodology-kit`（Public）**  
   - 内容 = 仅 **`methodology-kit/`**  
   - 给同事、论文「方法附录」引用。

2. **`your-org/ipp-research`（Private）**  
   - 内容 = 仓库根 **`README.md`** + **`methodology-kit/`** + **`stream2-analysis/`** + **`stream1a/`** + **`cross-stream/`**（**不含** **`archive/`**，该目录仅本机，见下）  
   - 用 **`.gitignore`** 忽略 **`archive/`** 并按合规排除其他敏感路径。

两个仓库之间：**公开 README 里写一句**「完整案例见内部私有仓库 / 某论文」，避免两套方法论漂移（以 **tag** 为准）。

### 私有库能和同事共享吗？

**可以。** 在 GitHub：仓库 **Settings → Collaborators** 添加对方 GitHub 账号（或把整个仓库交给 **Organization**，用 Team 管理权限）。常见权限：

| 角色 | 典型用途 |
|------|----------|
| **Read** | 只读克隆、拉取，适合仅需同步方法或旁观的同事 |
| **Write** | 可推送分支、提 PR，适合共同编码与写文档 |
| **Admin** | 管理协作者与分支保护，给负责人即可 |

私有库**不会**出现在你的公开主页的「公开仓库列表」里；受邀同事登录后可访问。**注意**：共享即视为对方可接触库内所有**未忽略**文件；若有人只需方法论，可只邀请访问 **公开** 的 `methodology-kit` 仓库，全量数据仍在私有库。

---

### 归档目录 `archive/`（仅本机）

课程 PDF、演示导出、原 `interview/` 与 `录音-文字/`、个人资料等，可放在 **`archive/`** 下便于整理；**默认不提交到任何 Git 仓库**（见根目录 `.gitignore`）。说明见 **`archive/README.md`**。

---

## 你现在最不容易晕的做法

1. **若目标只是「同事能拿到模板」** → 新建一个仓库，**只**把文件夹 **`methodology-kit/`** 推上去（策略 A）。  
2. **若目标还要备份 Stream 2 / 1A 代码与 MD** → 用策略 B 或 C，并**从第一天就写好 `.gitignore`**（含 **`archive/`**）；`archive/` 内材料请用网盘或本机备份，勿依赖 Git。

---

## 和「项目根目录」的关系说明

- 若你在 GitHub 创建仓库后，把**整个 `ipp` 文件夹**克隆到一个空目录里再复制文件：**仓库根** = 放 `methodology-kit`、`stream1a` 的那一层。  
- 若你只上传 **`methodology-kit`**：**仓库根**里就只有这一层目录（或把 `methodology-kit` 里的文件放在根目录，两种都可以，团队统一即可）。

更细的操作步骤（`git init`、`git add`）属于通用 Git 教程；需要时可在 MAINTAINER 里单独加一节。
