# 组件参考 · 完整 HTML/CSS 代码片段

每个组件给出完整的 CSS 和 HTML 示例，可直接复制使用。全局 CSS 变量和基础样式在每个文件头部声明一次即可。

> 示例中的文案均为通用占位内容，替换为你的实际内容即可。

## 全局基础样式

```html
<!doctype html>
<html lang="zh-HK">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=640,initial-scale=1">
<title>文章标题</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500&family=Noto+Sans+SC:wght@400;500;600;700&family=Noto+Serif+SC:wght@400;500;600;700;900&display=swap" rel="stylesheet">
<style>
:root {
  --accent: #1700AC; --lime: #D9FEA9; --red: #C90000; --green: #00BE62;
  --paper: #fafaf8; --ink: #0a0a0a; --grey-1: #f0f0ee; --grey-2: #d4d4d2; --grey-3: #737373;
  --serif: "Noto Serif SC", "Times New Roman", serif;
  --sans: "Noto Sans SC", "PingFang SC", "Microsoft YaHei", sans-serif;
  --mono: "IBM Plex Mono", ui-monospace, monospace;
}
* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  width: 640px; margin: 0 auto; background: #ffffff; color: var(--ink);
  font-family: var(--serif); font-size: 17px; line-height: 1.75;
  -webkit-font-smoothing: antialiased;
}
.container { padding: 0; }
</style>
</head>
<body>
<div class="container">
  <!-- 所有组件放这里 -->
</div>
</body>
</html>
```

---

## 1. 封面卡片 (Cover Card)

**用途**：文章顶部第一屏，制造视觉冲击。
**规则**：必须用靛蓝底，不能让封面是白底。

```css
.cover {
  background: var(--accent); color: #ffffff;
  padding: 56px 36px 48px; text-align: center;
}
.cover .cover-eyebrow {
  font-size: 14px; letter-spacing: 0.15em; opacity: 0.7; margin-bottom: 16px;
  font-family: var(--sans);
}
.cover .cover-title {
  font-size: 32px; font-weight: 900; line-height: 1.25; margin-bottom: 20px;
}
.cover .cover-sub {
  font-size: 17px; opacity: 0.8; line-height: 1.6; padding: 0 12px;
}
.cover .cover-bar {
  width: 48px; height: 4px; background: var(--lime); margin: 24px auto 0; border-radius: 2px;
}
```

```html
<div class="cover">
  <div class="cover-eyebrow">分类标签 · 栏目名</div>
  <div class="cover-title">你的文章主标题</div>
  <div class="cover-sub">副标题或日期信息</div>
  <div class="cover-bar"></div>
</div>
```

---

## 2. 章节头 (Chapter Header)

**用途**：每个大章节的开头。章节之间可加浅色背景或分割线区分。

```css
.chapter {
  padding: 40px 32px;
}
.chapter + .chapter {
  border-top: 1px solid var(--grey-2);
}
.chapter.accent-bg { background: #f6f4ff; }
.chapter.green-bg  { background: #f0faf4; }

.ch-num {
  font-size: 13px; letter-spacing: 0.15em; color: var(--accent); font-weight: 700;
  font-family: var(--sans); margin-bottom: 12px;
}
.ch-title {
  font-size: 26px; font-weight: 900; line-height: 1.3; margin-bottom: 8px;
}
.ch-sub {
  font-size: 16px; color: var(--grey-3); line-height: 1.6; margin-bottom: 28px;
}
```

```html
<div class="chapter">
  <div class="ch-num">一</div>
  <div class="ch-title">章节主标题</div>
  <div class="ch-sub">章节导语，一两句话概括本章要讲什么。</div>
  <!-- 章节内容放这里 -->
</div>
```

---

## 3. 子标题（左边框）

**用途**：章节内部的二级标题。

```css
.sub-title {
  font-size: 22px; font-weight: 700; margin: 36px 0 16px; padding-left: 14px;
  border-left: 4px solid var(--accent); line-height: 1.35;
}
.sub-title:first-child { margin-top: 0; }
```

```html
<div class="sub-title">这是一个子标题</div>
```

---

## 4. 警告卡 (Warning Card)

**用途**：风险提示、重要提醒、需要读者特别注意的内容。
**规则**：红色系，内容中可加粗强调关键词。

```css
.warn-card {
  background: #fff5f5; border-left: 4px solid var(--red);
  padding: 18px 20px; margin: 20px 0; border-radius: 0 8px 8px 0;
  font-size: 16px; line-height: 1.7; font-weight: 500;
}
.warn-card strong { color: var(--red); }
```

```html
<div class="warn-card">
  ⚠️ <strong>重要提醒：</strong>这里放需要读者特别注意的内容。关键信息用加粗标红突出。
</div>
```

---

## 5. 信息卡 (Info Card)

**用途**：补充说明、背景信息、温和提醒。

```css
.info-card {
  background: #f6f4ff; border-left: 4px solid var(--accent);
  padding: 18px 20px; margin: 20px 0; border-radius: 0 8px 8px 0;
  font-size: 16px; line-height: 1.7;
}
```

```html
<div class="info-card">
  💡 这里放补充说明或背景信息。语气比警告卡温和，用于解释或补充上下文。
</div>
```

---

## 6. 数据表 (Data Table)

**用途**：费用明细、条件对比、清单。
**规则**：上下粗线 + 行间细线。不超过 5 列（手机宽度限制）。

```css
.data-table {
  width: 100%; border-collapse: collapse; font-size: 14px; margin: 12px 0;
  border-top: 2px solid var(--ink); border-bottom: 2px solid var(--ink);
}
.data-table th {
  padding: 8px 4px; text-align: center; font-weight: 700;
  font-family: var(--sans);
}
.data-table td { padding: 8px 6px; vertical-align: top; }
.data-table tr { border-bottom: 1px solid var(--grey-2); }
.data-table tr:last-child { border-bottom: none; }
.data-table .col-label { font-weight: 700; text-align: left; }
.data-table .col-num { text-align: center; font-weight: 700; }
.data-table .col-note { color: var(--grey-3); font-size: 13px; }
```

```html
<table class="data-table">
<tr><th></th><th>方案 A</th><th>方案 B</th></tr>
<tr><td class="col-label">项目一</td><td class="col-num">¥1,000</td><td class="col-num">¥1,000</td></tr>
<tr><td class="col-label">项目二</td><td class="col-num">¥500</td><td class="col-num">¥800</td></tr>
<tr><td class="col-label">项目三</td><td class="col-num">无</td><td class="col-num" style="color:var(--red);">¥3,000</td></tr>
</table>
```

---

## 7. 金钱卡组 (Money Cards)

**用途**：并列展示不同金额/类型/条件。
**规则**：3 列 flex，每列不同边框色承载语义（绿/靛蓝/红）。

```css
.money-cards {
  display: flex; gap: 10px; margin: 20px 0;
}
.money-card {
  flex: 1; border-radius: 10px; padding: 20px 14px; text-align: center;
}
.money-card .mc-label {
  font-size: 13px; color: var(--grey-3); margin-bottom: 8px; font-family: var(--sans);
}
.money-card .mc-amount {
  font-size: 24px; font-weight: 900; margin-bottom: 4px;
}
.money-card .mc-cond {
  font-size: 13px; line-height: 1.5; color: var(--grey-3);
}
.mc-severance { background: #f0faf4; border: 2px solid var(--green); }
.mc-severance .mc-amount { color: var(--green); }
.mc-lsp { background: #f6f4ff; border: 2px solid var(--accent); }
.mc-lsp .mc-amount { color: var(--accent); }
.mc-notice { background: #fff5f5; border: 2px solid var(--red); }
.mc-notice .mc-amount { color: var(--red); }
```

```html
<div class="money-cards">
  <div class="money-card mc-severance">
    <div class="mc-label">类型 A</div>
    <div class="mc-amount">✓</div>
    <div class="mc-cond">条件说明文字<br>满足即可领取</div>
  </div>
  <div class="money-card mc-lsp">
    <div class="mc-label">类型 B</div>
    <div class="mc-amount">✓</div>
    <div class="mc-cond">条件说明文字<br>满足即可领取</div>
  </div>
  <div class="money-card mc-notice">
    <div class="mc-label">类型 C</div>
    <div class="mc-amount">✓</div>
    <div class="mc-cond">条件说明文字<br>满足即可领取</div>
  </div>
</div>
```

---

## 8. 分支流程图 (Branch Flow)

**用途**：决策树、「是/否」分叉选择。
**规则**：提问用靛蓝底白字居中 → 分叉 → 2-3 列选择卡。Yes 绿框，No 红框，备选紫框。

```css
.flow-q {
  background: var(--accent); color: #ffffff; text-align: center;
  padding: 16px 28px; border-radius: 10px; font-size: 19px; font-weight: 700;
  margin: 0 auto 12px; max-width: 320px;
}
.flow-split {
  width: 2px; height: 20px; background: var(--grey-2); margin: 0 auto;
  position: relative;
}
.flow-split::after {
  content: ''; position: absolute; bottom: -1px; left: -4px;
  border-left: 5px solid transparent; border-right: 5px solid transparent;
  border-top: 8px solid var(--grey-2);
}
.flow-branch {
  display: flex; gap: 10px; margin: 8px 0 28px;
}
.flow-branch .branch {
  flex: 1; border-radius: 12px; padding: 20px 16px; font-size: 15px; line-height: 1.65;
}
.branch-yes { background: #f0faf4; border: 2px solid var(--green); }
.branch-no  { background: #fff5f5; border: 2px solid var(--red); }
.branch-alt { background: #f6f4ff; border: 2px solid var(--accent); }
.branch .br-tag {
  font-family: var(--sans); font-size: 12px; letter-spacing: 0.1em; font-weight: 700;
  margin-bottom: 8px;
}
.branch-yes .br-tag { color: var(--green); }
.branch-no  .br-tag { color: var(--red); }
.branch-alt .br-tag { color: var(--accent); }
.branch .br-title { font-weight: 700; font-size: 18px; margin-bottom: 8px; }
```

```html
<div class="flow-q">你的决策问题？</div>
<div class="flow-split"></div>
<div class="flow-branch">
  <div class="branch branch-yes">
    <div class="br-tag">→ 是</div>
    <div class="br-title">路径 A</div>
    <div>选择「是」之后的操作步骤描述。</div>
  </div>
  <div class="branch branch-no">
    <div class="br-tag">→ 否</div>
    <div class="br-title">路径 B</div>
    <div>选择「否」之后的操作步骤描述。</div>
  </div>
</div>
```

---

## 9. Q&A 块 (QA Block)

**用途**：集中解答高频疑问。
**规则**：Q 靛蓝底白字，A 浅灰底正文，上下拼接。

```css
.qa-block { margin: 24px 0; }
.qa-q {
  font-weight: 700; font-size: 18px; color: #ffffff; background: var(--accent);
  padding: 16px 20px; border-radius: 10px 10px 0 0;
}
.qa-a {
  background: #fafaf8; padding: 18px 20px; border-radius: 0 0 10px 10px;
  font-size: 16px; line-height: 1.7;
}
```

```html
<div class="qa-block">
  <div class="qa-q">这是一个常见问题？</div>
  <div class="qa-a">这是详细解答。<strong>关键结论加粗。</strong>可以多写几句把情况说清楚。</div>
</div>
```

---

## 10. 大字报 (Big Quote)

**用途**：核心观点强调、一句话总结、行动号召。
**规则**：柠绿底 + 靛蓝字。字号 24px+，居中。

```css
.big-quote {
  font-size: 24px; font-weight: 700; line-height: 1.4;
  text-align: center; padding: 32px 24px;
  background: var(--lime); border-radius: 10px; color: var(--accent);
  margin: 32px 0;
}
```

```html
<div class="big-quote">
  核心观点一句话总结。<br>柠绿底靛蓝字，居中醒目。
</div>
```

---

## 11. 口诀块 (Mnemonic Block)

**用途**：易记的操作要点总结。
**规则**：靛蓝底白字圆角卡片，关键词用柠绿 `<span>` 高亮。

```css
.mnemonic {
  background: var(--accent); color: #ffffff; border-radius: 10px;
  padding: 20px 28px; margin: 28px 0; text-align: center;
  font-size: 17px; font-weight: 600; letter-spacing: 0.04em; line-height: 1.6;
}
.mnemonic span { color: var(--lime); }
```

```html
<div class="mnemonic">
  简单记：<span>关键词一</span>、<span>关键词二</span>、<span>关键词三</span>。总结性语句。
</div>
```

---

## 12. 带编号步骤 (Numbered Steps)

**用途**：操作流程、分步指南。
**规则**：圆形靛蓝数字（44×44px）+ 右侧标题及正文。每个步骤 margin-bottom 24px。

```css
.gap-steps { margin: 24px 0; }
.gap-step {
  display: flex; gap: 16px; margin-bottom: 24px;
}
.gap-step:last-child { margin-bottom: 0; }
.gs-num {
  flex-shrink: 0; width: 44px; height: 44px; border-radius: 50%;
  background: var(--accent); color: #fff; font-size: 20px; font-weight: 900;
  display: flex; align-items: center; justify-content: center;
}
.gs-body { flex: 1; padding-top: 4px; }
.gs-body .gs-title { font-size: 19px; font-weight: 700; margin-bottom: 6px; }
.gs-body p, .gs-body li { font-size: 15px; line-height: 1.65; color: #333; }
.gs-body ul { padding-left: 18px; }
.gs-body li { margin-bottom: 6px; }
```

```html
<div class="gap-steps">
  <div class="gap-step">
    <div class="gs-num">1</div>
    <div class="gs-body">
      <div class="gs-title">第一步标题</div>
      <ul>
        <li>操作要点一</li>
        <li>操作要点二</li>
      </ul>
    </div>
  </div>
  <div class="gap-step">
    <div class="gs-num">2</div>
    <div class="gs-body">
      <div class="gs-title">第二步标题</div>
      <p>步骤说明文字。</p>
    </div>
  </div>
</div>
```

---

## 13. 快速对照卡 (Quick Reference Card)

**用途**：多条信息的快速索引。
**规则**：浅灰底，每行：彩色标签 + 主文 + 备注。

```css
.quick-card {
  background: #fafaf8; border-radius: 12px; padding: 24px; margin: 20px 0;
}
.quick-row {
  display: flex; gap: 8px; padding: 12px 0; border-bottom: 1px solid var(--grey-2);
  font-size: 15px; line-height: 1.5;
}
.quick-row:last-child { border-bottom: none; }
.ql-tag {
  flex-shrink: 0; padding: 2px 10px; border-radius: 4px;
  font-size: 13px; font-weight: 700; font-family: var(--sans);
  color: #ffffff;
}
.ql-tag.a { background: var(--green); }
.ql-tag.b { background: var(--red); }
.ql-tag.c { background: var(--accent); }
.ql-tag.d { background: var(--grey-3); }
.ql-body { flex: 1; }
.ql-body .ql-main { font-weight: 600; }
.ql-body .ql-note { font-size: 13px; color: var(--grey-3); margin-top: 2px; }
```

```html
<div class="quick-card">
  <div class="quick-row">
    <span class="ql-tag a">标签A</span>
    <span class="ql-body"><span class="ql-main">主要内容摘要</span><br><span class="ql-note">补充说明文字</span></span>
  </div>
  <div class="quick-row">
    <span class="ql-tag b">标签B</span>
    <span class="ql-body"><span class="ql-main">主要内容摘要</span><br><span class="ql-note">补充说明文字</span></span>
  </div>
  <div class="quick-row">
    <span class="ql-tag c">标签C</span>
    <span class="ql-body"><span class="ql-main">主要内容摘要</span><br><span class="ql-note">补充说明文字</span></span>
  </div>
</div>
```

---

## 14. CTA 尾卡 (CTA Footer)

**用途**：文章末尾的行动号召。
**规则**：靛蓝底白字，列出可提供的帮助。**每篇文章必须以此结尾。**

```css
.cta-card {
  background: var(--accent); color: #ffffff; border-radius: 14px;
  padding: 32px 28px; text-align: center; margin: 32px 0;
}
.cta-card .cta-title { font-size: 20px; font-weight: 700; margin-bottom: 12px; }
.cta-card p { font-size: 16px; line-height: 1.7; opacity: 0.9; margin-bottom: 16px; }
.cta-card .cta-items { display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 20px; }
.cta-card .cta-item {
  background: rgba(255,255,255,0.12); padding: 8px 16px; border-radius: 20px;
  font-size: 14px; font-family: var(--sans);
}
.cta-card .cta-footer { font-size: 13px; opacity: 0.7; line-height: 1.8; }
```

```html
<div class="cta-card">
  <div class="cta-title">我们能帮你什么？</div>
  <p>通过以下方式联系我们：</p>
  <div class="cta-items">
    <span class="cta-item">📋 服务项目一</span>
    <span class="cta-item">📊 服务项目二</span>
    <span class="cta-item">📅 服务项目三</span>
    <span class="cta-item">📞 服务项目四</span>
    <span class="cta-item">📲 服务项目五</span>
  </div>
  <div class="cta-footer">
    你的组织名 · 口号<br>转发给需要的人 🤝
  </div>
</div>
```

---

## 15. 落款 (Byline)

**用途**：文章最末尾的组织署名和参考来源。
**规则**：居中浅灰色小字。放在 `</div><!-- .container -->` 之前。

```css
.byline { text-align: center; font-size: 14px; color: var(--grey-3); padding: 20px 32px 8px; }
.sources { padding: 20px 32px 40px; border-top: 1px solid var(--grey-2); }
.sources .src-title { font-size: 13px; color: var(--grey-3); font-weight: 700; margin-bottom: 8px; }
.sources p { font-size: 12px; color: var(--grey-3); line-height: 1.7; margin-bottom: 3px; }
```

```html
<div class="byline">
  你的组织名 · 口号<br>转发给需要的人 🤝
</div>
<div class="sources">
  <div class="src-title">参考来源</div>
  <p>· 来源一</p>
  <p>· 来源二</p>
</div>
```

---

## 组件组合规则

1. **每篇文章必须包含**：封面卡片 + 至少一个章节头 + CTA 尾卡
2. **避免连续单调**：同一类型组件不要连续使用 3 次以上
3. **字号对比**：标题 26-32px → 子标题 22px → 正文 17px → 辅助文字 13-15px
4. **色彩呼吸**：在两段靛蓝/红色重组件之间插入一段浅色/白底段落，让眼睛休息
5. **手机预览**：做完后在浏览器缩到 375px 宽度模拟手机，确认表格不溢出、字号不小于 13px
