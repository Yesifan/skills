# Skills

Agent Skills 仓库，使用 `npx skills` 发现和安装。

## 安装

需要已安装 Node.js，并可使用 `npx`。运行以下命令选择要安装的 skill 和目标 agent：
```sh
npx skills add Yesifan/skills
```

## 目录
```text
.
├── AGENTS.md   # For Agent
├── README.md   # For Human
└── skills/ 
    └── <skill-name>/
        └── SKILL.md 
```

## Skill 索引

- [deliberate](skills/deliberate/SKILL.md): 复杂任务的通用行为准则。 [Source](https://github.com/multica-ai/andrej-karpathy-skills)
- [writing-doc](skills/writing-doc/SKILL.md): 面向 agent 的文档编写准则，关注内容取舍、信息组织与维护成本。
- [spec](skills/spec/SKILL.md): 将讨论整理为 spec，维护状态、执行时间与索引，并提供 README 和 AGENTS.md 初始化规则。 [Source](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md)
- [setup-adr](skills/setup-adr/SKILL.md): 一次性将 ADR 与可选术语表的收录边界和维护规则写入项目 AGENTS.md。 [Source](https://github.com/mattpocock/skills/blob/main/docs/engineering/domain-modeling.md)
