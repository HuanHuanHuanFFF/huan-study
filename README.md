# Huan Study

一组面向计算机基础、技术原理和后端面试学习的 Agent Skills。

三个 Skill 共享 `huan-study` 前缀，但彼此独立，没有固定执行顺序。你可以只听讲、单独检验理解，或在需要时整理总结。

## Skills

| Skill | 作用 | 触发方式 |
| --- | --- | --- |
| `huan-study-teach` | 从问题与设计压力出发，建立少而准的因果模型 | 支持自动匹配和显式调用 |
| `huan-study-grill` | 通过逐轮追问检验独立复述、迁移和追问能力 | 仅显式调用 |
| `huan-study-summary` | 将学习对话整理成全量、增量或修订版 Markdown 总结 | 仅显式调用 |

## 安装

### ChatGPT / Work

可以把整个仓库作为 `Huan Study` Plugin 安装。Plugin 会同时提供三个 Skill，并保留各自调用策略。

也可以只安装需要的 Skill 子目录：

```text
@skill-creator 请安装这个仓库 skills 目录中的 huan-study-teach、huan-study-grill 和 huan-study-summary。
```

### Codex CLI / IDE Extension

优先把整个仓库作为 Plugin 安装。若只需要单个 Skill，也可以让 `$skill-installer` 安装 `skills/` 下的对应子目录，或把它复制到：

```text
$HOME/.agents/skills/
```

更多格式、调用与安装规则见 [OpenAI Skills 文档](https://learn.chatgpt.com/docs/build-skills)。

## 使用

ChatGPT 使用 `@skill-name`，Codex CLI 和 IDE Extension 使用 `$skill-name`。例如：

```text
@huan-study-teach 为什么线程切换通常比进程切换轻？
@huan-study-grill 检查我是否真正理解了 TCP 三次握手。
@huan-study-summary 把本次学习对话整理成增量 Markdown 总结。
```

`huan-study-teach` 允许模型根据任务自动匹配。`huan-study-grill` 与 `huan-study-summary` 仅在用户显式调用时运行。

## 结构

```text
huan-study/
├── .codex-plugin/
│   └── plugin.json
└── skills/
    ├── huan-study-teach/
    │   ├── SKILL.md
    │   └── agents/openai.yaml
    ├── huan-study-grill/
    │   ├── SKILL.md
    │   └── agents/openai.yaml
    └── huan-study-summary/
        ├── SKILL.md
        └── agents/openai.yaml
```

Plugin 通过 `.codex-plugin/plugin.json` 发现整个 Skill 组。每个 `skills/` 子目录仍可独立安装：

- `SKILL.md` 定义触发范围与执行规则。
- `agents/openai.yaml` 定义界面名称、默认调用示例和隐式触发策略。

## 设计原则

- 一次只解决一个核心问题。
- 先建立因果主干，再扩展属性、历史和面试话术。
- 目标是让用户能复述、迁移并应对追问。
- 教学、检验和总结保持独立，不强制组成工作流。

## 致谢

`huan-study-grill` 的早期设计受到 [Matt Pocock 的 grilling Skill](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling) 启发，随后针对单轮认知负担与技术学习场景做了轻量改造。

## License

[MIT](LICENSE) © 2026 HuanHuanHuanFFF
