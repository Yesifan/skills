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
- [writing-doc](skills/writing-doc/SKILL.md): 面向 agent 的文档编写准则，关注内容取舍、信息组织与维护成本。 [Source](https://github.com/mattpocock/skills/blob/main/skills/productivity/writing-for-agents/SKILL.md)
