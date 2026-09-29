# 仓库约定

这是 Agent Skills 仓库, skill 面向 GPT-6 Astra 等高智能模型。

## 编写原则

- Skill default to using English.
- 名称与目录保持一致，使用小写字母、数字和连字符
- 默认模型具备通用能力，只补充会改变决策的领域知识、工具约束和个人偏好。
- 默认设置 `skill` 为 `disable-model-invocation: true`，同时设置面向 `codex` 的 `agents/openai.yaml` 


## 维护

- 每次新增 skill，同步在 README.md 的 Skill 索引中添加指向该 skill 的 `SKILL.md` 的相对链接和一句简要用途说明；重命名、删除或调整用途时同步更新对应条目。

## 参考

- [OpenAI 的 Astra 指南](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)
