# 校园招聘邮件投递助手（Campus Apply Email Skill）

一个开箱即用的 [Agent Skill](https://agentskills.io)，让你的 AI 编码助手（Claude Code / ZCode 等）自动生成规范的校招投递邮件。

秋招海投时，每家公司的邮件格式要求都不一样：有的要求 `姓名-学校-专业-岗位-毕业时间`，有的要求复制一串带编码的主题，还有的直接发一张截图说明规则。本技能把这些规则沉淀成 AI 可复用的模板——你只需把**简历**和**招聘信息（JD/截图）**丢给 AI，它就能输出可直接发送的收件人、邮件主题和正文。

> **English:** An open-source [Agent Skill](https://agentskills.io) that turns your resume + job description into a ready-to-send campus recruitment application email (recipient, subject, and body), following each company's own subject-format rules. Works with any AI coding assistant that supports the Agent Skills format (Claude Code, ZCode, ...). See [SKILL.md](SKILL.md) — documentation is mostly in Chinese.

## 功能特性

- **邮件主题**：默认生成 `姓名-学校-专业-应聘岗位-毕业时间` 格式；企业有明确规定时严格照抄企业规则
- **收件人提取**：自动从公告/截图中提取投递邮箱
- **正文生成**：简短版（5-7 句）与标准版两种模板，内容严格匹配你的简历与 JD，不虚构经历
- **规则沉淀**：把某家公司的投递要求固化下来，下次投递直接复用
- **输出完整**：每次输出收件人 + 主题 + 正文，可选附件清单与投递注意事项

## 安装

把本仓库克隆或下载后，将 `SKILL.md` 放入你的 AI 助手的技能目录：

**Claude Code**

```bash
# 个人全局技能
git clone https://github.com/<your-name>/campus-apply-email-skill.git ~/.claude/skills/campus-apply-email
```

**ZCode**

```bash
# 项目级技能（仅当前工作区可用）
git clone https://github.com/<your-name>/campus-apply-email-skill.git .zcode/skills/campus-apply-email
```

其他支持 [Agent Skills](https://agentskills.io) 格式的工具同理：把整个目录放进它的 skills 目录即可。

## 使用

装好后直接用自然语言对话：

```text
帮我根据这份简历和这个 JD 生成一封投递邮件，简短版。
（附上简历 PDF / 文本，以及岗位信息或截图）
```

AI 会输出：

```text
收件人：hr@example.com
邮件主题：李雷-示例大学-计算机科学与技术-AI应用开发工程师-2027年6月
邮件正文：
尊敬的招聘负责人：
您好！我是李雷，……
```

检查无误后，复制到邮箱客户端、附上 PDF 简历即可发送。

## 自定义

- 想为某家公司固化投递规则？对该 AI 说「把这个投递规则沉淀成 Skill」，它会按本技能的格式保存为专属规则。
- 想调整默认主题格式或正文语气？直接修改 `SKILL.md` 中「核心规则」与「输出模板」两节即可。

## 隐私与安全

- 本技能只是**纯文本模板 + 规则**，不联网、不收集、不上传任何信息。
- 仓库中所有示例（人名、学校、邮箱等）均为虚构，仅作演示。
- 生成结果包含你的真实联系方式，请仅用于向目标企业投递；**不要把真实简历信息提交到公开仓库**。

## License

[MIT](LICENSE)
