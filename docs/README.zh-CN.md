# 对抗式工程管理技能

**质疑计划，审查改动，用证据证明结果。**

[English](../README.md) · 简体中文 · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

面向编码 Agent 的工程管理技能，将项目中的对抗自检实践提炼成三道可追溯的质量门禁。它要求审查者找出具体失败路径，并由主 Agent 逐项修复，或用证据说明为什么驳回。

## 三道门禁

1. **计划自检**：实质性实现开始前，检查约束、接口与数据契约、权限、状态转换、遗漏的使用方和过度设计。
2. **改动审查**：每个完整批次完成后、合并前，审查实际 diff 和受影响行为；涉及安全边界时增加专项审查。
3. **验收核证**：宣称完成前，用当前运行结果或产物检查支持结论，并说明没有检查的部分。

小改动采用小检查，高风险改动采用独立视角和可单独验收的批次。自审必须明确标记，不能替代项目要求的独立审查。未解决的阻塞项不能算通过。技能不会授予部署、发布或其他外部操作权限。

## 安装

安装 Git 和 Node.js/npm 后，在目标项目目录运行：

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

交互选择 Agent；可追加 `-a claude-code`、`-a codex` 或 `-a cursor` 指定目标，追加 `--copy` 避免符号链接，追加 `-g` 安装到用户范围。Copilot、Gemini CLI、OpenCode、Cline、Windsurf 等选项，以及手动安装和卸载方法，见[安装指南](INSTALL.md)。支持范围以第三方 Skills CLI 的当前列表为准，不表示所有 Agent 均经过端到端验证。

## 使用

> 请用 adversarial-engineering 处理这项改动：实现前挑战计划，完成后审查 diff，交付前核验验收结论。逐条记录发现的处置与证据，并说明未验证的部分。

仅需审查时补充“不要修改文件”。已有证据仍有效时不重复测试；只针对已改问题复审，有新证据或实质性修订才继续审查。

[英文 SKILL.md](../skills/adversarial-engineering/SKILL.md) 是唯一规范源；本页是介绍和安装说明，不是另一份技能。它不是无缺陷保证，也不是自动执行的 CI 门禁。见[验证范围](VALIDATION.md)、[贡献指南](../CONTRIBUTING.md)和 [MIT 许可证](../LICENSE)。欢迎母语审校。
