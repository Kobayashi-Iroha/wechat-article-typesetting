# 微信公众号排版 Skill

> Claude Code Skill — 将文字草稿转化为 640px 杂志级公众号长图文 HTML

## 这是什么

一个给 Claude Code 用的排版 skill。告诉 Claude 你要写什么主题的公众号文章，它会按照一套经过实战验证的组件体系，直接输出一份可直接粘贴到微信公众号后台的 HTML 文件。

不是「AI 随便排一下」——每个组件（封面卡片、警告卡、数据表、流程图、Q&A、CTA 尾卡等）都有固定的 HTML/CSS 规范和语义规则，保证输出质量和品牌一致性。

## 包含什么

```
wechat-article-typesetting/
├── SKILL.md                              ← Skill 主文件（排版规则 + 工作流程）
├── README.md                             ← 本文件
├── assets/
│   └── template-wechat-article.html      ← 种子模板（15 组件 CSS + HTML 骨架，复制即用）
└── references/
    ├── components-reference.md           ← 每个组件的 HTML/CSS 代码片段查阅
    └── example-articles.md               ← 已完成贴文的组件拆解和模式分析
```

## 适用场景

- 微信公众号 640px 长图文排版
- 操作指南、费用说明、普法教育、决策辅助等实用类内容
- 需要品牌一致的视觉风格（杂志感、卡片式、色彩语义化）

## 不适用

- 纯娱乐/情感/生活类内容（排版风格偏严肃实用）
- 小红书图文卡片（用 `guizang-social-card-skill`）
- 视频脚本、PPT 等其他形式

## 设计系统

| 令牌 | 值 | 语义 |
|------|-----|------|
| 深靛蓝 | `#1700AC` | 品牌主色、封面、标题、CTA |
| 柠绿 | `#D9FEA9` | 高亮强调、大字报背景 |
| 翠绿 | `#00BE62` | 正确/合法/可行 |
| 红色 | `#C90000` | 风险/警告/禁止 |
| 纸白 | `#fafaf8` | 卡片底色 |
| 墨黑 | `#0a0a0a` | 正文 |

字体：Noto Serif SC（正文）+ Noto Sans SC（标签）+ IBM Plex Mono（数据）

## 安装使用

1. 将整个 `wechat-article-typesetting/` 文件夹放入 Claude Code 项目的 `.claude/skills/` 目录
2. 在对话中说「用排版 skill 做一篇 XX 贴文」或直接描述内容
3. Claude 会自动加载 skill 并按规范输出 HTML 文件

## 相关

- 品牌标准：`brand-social-card-standards` (memory)
- 工作流规范：`wechat-article-workflow` (memory)
- 写作原则：`account-stance-writing-principles` (memory)
- 社交卡片：`guizang-social-card-skill`
