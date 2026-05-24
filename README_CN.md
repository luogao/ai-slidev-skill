# AI + Slidev Skill 🎤

> 教 AI 用 [Slidev](https://github.com/slidevjs/slidev) 自动生成专业演示文稿的 Agent Skill

[English](README.md) | 中文

[![Skills](https://img.shields.io/badge/skills.sh-ai--slidev-blue)](https://www.skills.sh/luogao/ai-slidev-skill)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**说一句话 → 一份 Markdown → 一套专业 PPT，不到一分钟。**

## 它能做什么

这个 Skill 教任何 AI Agent（Claude Code、Codex、Cursor、GitHub Copilot 等）如何：

1. **理解你的主题** — 自动收集需求或从上下文推断
2. **生成 Slidev Markdown** — 完整的 `slides.md`，包含布局、代码块、演讲备注
3. **选择合适的主题** — 暗色科技风、商务简约风、或自定义品牌色
4. **一键导出** — PDF、SPA 网页、PNG 图片

## 效果演示

> 用 AI + Slidev 做的一个 PPT 技巧分享视频（30 秒）

**一句话生成 → 自动排版 → 导出 PDF，整个过程不到一分钟。**

## 快速开始

### 安装 Skill

```bash
# 使用 skills CLI 安装
npx skills add https://github.com/luogao/ai-slidev-skill

# 或者手动复制到你的 agent skill 目录
```

### 使用

直接跟你的 AI Agent 说：

> "帮我做一个关于 React 性能优化的演示文稿，10 页"

装了这个 Skill 的 Agent 会自动：
1. 生成完整的 `slides.md` 文件
2. 帮你初始化 Slidev 项目
3. 预览、迭代、导出

### 手动使用

```bash
# 创建项目
mkdir my-talk && cd my-talk
npm init slidev@latest

# 把 AI 生成的 Markdown 粘贴到 slides.md
# 启动开发服务器（支持热更新）
npm run dev

# 导出为 PDF
npm run export
```

## 项目结构

```
ai-slidev-skill/
├── SKILL.md                        # 核心指令（AI 读取这个文件）
├── references/
│   ├── slidev-syntax.md            # Slidev Markdown 完整语法参考
│   └── prompt-templates.md         # 7 种场景的 AI prompt 模板
├── assets/
│   └── themes/                     # 预置主题配置
│       ├── dark-tech.json          # 暗色科技风
│       └── corporate.json          # 商务简约风
├── examples/
│   └── demo-slides.md              # 示例演示文稿
└── README.md
```

## Prompt 模板

| 模板 | 适用场景 |
|------|----------|
| 快速生成 | 任意主题，快速出稿 |
| 技术演讲 | 含代码演示的开发者演讲 |
| 商业路演 | 创业融资、产品发布 |
| 教程工作坊 | 动手教学 + 练习 |
| 闪电演讲 | 5 分钟会议快讲 |
| 学术论文 | 含数学公式的论文报告 |
| 内容转换 | 把文章/笔记转成 PPT |

## 支持的 Agent

兼容所有支持 [Agent Skills 规范](https://agentskills.io/specification) 的 Agent：

- ✅ Claude Code
- ✅ OpenAI Codex
- ✅ Cursor
- ✅ GitHub Copilot
- ✅ Windsurf
- ✅ Cline
- ✅ 任何支持 SKILL.md 的 Agent

## 为什么选 Slidev？

| 特性 | PowerPoint | Slidev |
|------|-----------|--------|
| 格式 | `.pptx` 二进制 | `.md` 纯文本 |
| 版本控制 | ❌ | ✅ Git 友好 |
| AI 自动生成 | 难以自动化 | 天然 Markdown 输出 |
| 代码展示 | 丑陋的截图 | 语法高亮、可交互 |
| 开发者体验 | 只能 GUI | CLI + 热更新 |
| 主题生态 | 贵 | 免费开源 |
| 导出 | 内置 | PDF / SPA / PNG |

## 许可证

MIT © [luogao](https://github.com/luogao)
