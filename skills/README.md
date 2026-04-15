# Skill 草稿（Cursor / Claude Code 等）

面向**使用工具包的同事**：若希望在 IDE 里用自然语言触发「E/C 辨析」「新数据准入」「阶段闸门」，可将下列文件安装为 Skill。工具包总览见上级目录 [README.md](../README.md)。

将下列 `.md` 复制到本机技能目录即可使用（路径以 Cursor 为例：`~/.cursor/skills/{name}/SKILL.md`）。

| 文件 | 建议目录名 | 用途 |
|------|------------|------|
| `qec-e-vs-c/SKILL.md` | `qec-e-vs-c` | 编码时辨析 E 与 C |
| `domain-adaptation-intake/SKILL.md` | `domain-adaptation-intake` | 新数据源先填准入问卷 |
| `methodology-gate-check/SKILL.md` | `methodology-gate-check` | 阶段闸门自检（可追溯/可复制） |

复制后可在各 `SKILL.md` 顶部的 `description` 里加上你们团队常用触发语。

**注意**：Skill 内请用**相对路径或固定 tag** 指向 `methodology-kit` 母本，避免与 `stream2-analysis/docs/` 两套说法漂移；母本以 Git **tag** 为准最佳。

