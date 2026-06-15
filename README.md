# 项目化教学设计师 Skill

`vocational-project-teaching-designer` 是一个面向职业教育与本科教学的 Codex Skill，用于把传统的知识点、教材章节或课程单元转化为项目化教学设计，并最终生成一个浅色风格的教学过程实时交互网页。

## 适用场景

- 中职、高职、本科课程的项目化教学改造。
- 将传统章节内容转化为真实项目、工作任务和学习任务。
- 生成任务技能对照表、关键/难点技能点展示、任务知识点对照表和重点/难点知识点详解。
- 使用 Image2 生成项目技能思维导图与知识思维导图，并插入网页。
- 使用 Remotion 插件生成重点或难点知识的教学参考动画。
- 设计任务验收标准、评分量表和课堂过程性评价。
- 输出可本地运行的教学过程交互网页。

## 输入要求

使用该 Skill 时，建议提供以下信息：

- 教学对象层次：中职、高职或本科。
- 传统教学内容：教材章节、知识点、课程单元、实训模块或课程标准片段。
- 可选约束：学时、专业方向、已有设备或软件、考核方式、区域产业背景。

示例提示：

```text
Use $vocational-project-teaching-designer，将“PLC 基本指令与电机启停控制”面向高职学生转化为项目化教学设计，并生成交互式教学网页。
```

## 安装前准备

为了完整生成最终网页，请在安装或使用本 Skill 前确认：

- 已启用 Image2 或等效图片生成能力，用于生成技能思维导图和知识思维导图图片。
- 已安装并启用 Remotion 插件，用于生成教学参考动画。

如果缺少上述能力，本 Skill 仍可生成项目、任务、技能、知识和评价文本，但最终网页中的思维导图与动画只能作为临时文本占位，不能达到完整效果。

## 工作流程

1. 根据教学对象和传统内容生成 3-5 个候选项目，等待用户选择确认。
2. 将已确认项目拆解为 4-8 个任务，并等待用户确认任务分解。
3. 逐项分析任务所需技能，生成项目任务技能对照表。
4. 提炼关键/难点技能点，展示技能内容、示范步骤、练习活动、常见错误和掌握证据。
5. 分析技能背后的知识支撑，生成任务知识点对照表和重点/难点知识点详解。
6. 建立知识点与技能点的对应关系，说明知识如何支撑任务表现。
7. 调用 Image2 生成项目技能思维导图图片。
8. 调用 Image2 生成项目知识思维导图图片，并用 `★` 标记重点知识、用 `▲` 标记难点知识。
9. 调用 Remotion 插件生成重点和难点知识的教学参考动画。
10. 设计项目验收标准和各任务验收表格。
11. 按教学过程顺序生成浅色背景的实时交互网页。

## 目录结构

```text
vocational-project-teaching-designer/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── interactive-page-template.html
└── references/
    └── project-teaching-method.md
```

## 文件说明

- `SKILL.md`：Skill 主说明文件，定义触发条件、输入要求和完整工作流。
- `agents/openai.yaml`：Codex UI 中展示 Skill 的元数据。
- `references/project-teaching-method.md`：项目化教学设计方法参考，包括层次校准、任务拆解、技能分析、知识支撑、动画设计和评价设计规则。
- `assets/interactive-page-template.html`：最终交互式教学网页的基础模板，可在生成具体课程网页时复用。

## 安装方式

将本仓库克隆或复制到 Codex 的 Skills 目录中，例如：

```powershell
git clone https://github.com/jh0262/vocational-project-teaching-designer.git "$env:USERPROFILE\.codex\skills\vocational-project-teaching-designer"
```

安装后，在 Codex 中使用 `$vocational-project-teaching-designer` 调用该 Skill。

安装完成后建议先做一次能力检查：让 Codex 确认 Image2 可用于生成图片，Remotion 插件可用于创建和渲染教学动画。

## 设计特点

- 采用“先确认项目、再确认任务”的交互式教学设计流程。
- 强调职业教育中的工作过程、技能证据和验收标准。
- 专门呈现重点、难点的知识点与技能点，便于教师组织讲解、示范、练习和评价。
- 兼顾中职、高职、本科三个层次的项目难度与知识深度。
- 最终产物不仅是文本方案，还包括 Image2 思维导图、Remotion 教学动画和可直接打开的教学过程交互网页。
