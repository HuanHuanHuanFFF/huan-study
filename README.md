# Huan Study

一组用于计算机基础、技术原理和后端面试学习的 Agent Skills。

技术学习的难点不只是获得解释：听懂不等于能够独立复述，能够复述也不等于能够迁移到新问题，按时间顺序保存聊天记录更不等于形成了可复用的知识结构。Huan Study 为这三种学习需要提供彼此独立的入口。

让 Agent 介绍：

```text
使用 https://github.com/HuanHuanHuanFFF/huan-study 中的 huan-study-teach，讲一下这组 Skills 分别解决什么问题、应该如何选择。
```

## 选择 Skill

三个 Skill 没有固定执行顺序。可以只使用其中一个，也可以在解释完成后检验理解，再把有价值的内容整理成总结。

| Skill | 什么时候用 | 触发方式 |
| --- | --- | --- |
| `huan-study-teach` | 需要建立概念模型或获得通用讲解 | 自动匹配或显式调用 |
| `huan-study-grill` | 想通过讲解和追问确认自己是否真正理解 | 仅显式调用 |
| `huan-study-summary` | 想总结会话知识，方便后续复用和查询 | 仅显式调用 |

## 使用示例

```text
为什么线程切换通常比进程切换轻？（通用讲解可自动匹配 huan-study-teach，无需显式指定）
使用 huan-study-grill，检查我是否真正理解了 TCP 三次握手。
使用 huan-study-summary，把本次学习对话整理成增量 Markdown 总结。
```

## 安装

仓库采用标准 skills-only Plugin 结构，可以在 [skills.sh 集合页](https://skills.sh/huanhuanhuanfff/huan-study) 查看全部三个 Skill。

Skills CLI：

```powershell
npx --yes skills add HuanHuanHuanFFF/huan-study --skill '*' --agent codex --global --yes
```

让 Agent 安装：

```text
请安装 https://github.com/HuanHuanHuanFFF/huan-study 仓库中的全部 Skills。
```

如需独立安装，可以要求 Agent 只安装 `skills/` 下的指定 Skill。安装或更新后，请重新启动 Codex 或新建任务，使 Skills 被重新发现。

## 仓库结构

```text
huan-study/
├── .codex-plugin/plugin.json
├── README.md
├── LICENSE
└── skills/
    ├── huan-study-teach/
    ├── huan-study-grill/
    └── huan-study-summary/
```

每个 Skill 子目录都包含独立的 `SKILL.md` 和 `agents/openai.yaml`。前者定义执行规则，后者定义界面信息和触发策略。

## 致谢

`huan-study-grill` 的早期主动回忆设计受到 [Matt Pocock 的 grilling Skill](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) 和 “Grill Me” 工作方式启发，随后针对单轮认知负担、技术学习和知识迁移进行了改造。

## 许可

[MIT](LICENSE) © 2026 HuanHuanHuanFFF
