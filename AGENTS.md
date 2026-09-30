# 仓库约定

这是 Agent Skills 仓库, skill 面向 GPT-6 Astra 等高智能模型。

## 编写原则

- 创建 skills 时参考 [skill-creator](./skills/skill-creator/) skill
- 创建 skill 是先使用中文讨论和落盘，最终提交时整理为英语
- skill 默认不被 agent 发现
  - 默认设置 `skill` 为 `disable-model-invocation: true`
  - 设置面向 `codex` 的 `agents/openai.yaml` 配置


## 维护

- 维护 [skills sh 配置文件](./skills.sh.json)
- 每次新增 skill，同步在 README.md 的 Skill 索引中添加指向该 skill 的 `SKILL.md` 的相对链接和一句简要用途说明；重命名、删除或调整用途时同步更新对应条目。

## 参考

- [OpenAI 的 Astra 指南](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)
