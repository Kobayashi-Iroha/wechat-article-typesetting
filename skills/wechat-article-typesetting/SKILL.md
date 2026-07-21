---
name: wechat-article-typesetting
description: 微信公众号 640px 长图文排版。Generate polished WeChat Official Account long-form articles (640px width) with a magazine-editorial component system — cover cards, warning/info cards, money cards, flow charts, QA blocks, mnemonics, quick-reference cards, and CTA footers. Use when the user asks for 公众号排版, 公众号贴文, 微信文章排版, WeChat article formatting, or a 640px HTML article.
---

# 微信公众号排版 Skill

将草稿文字转化为 640px 宽、手机竖屏阅读优化的公众号长图文 HTML。输出一份自包含的 HTML 文件，可直接粘贴到微信公众号后台。

## 核心理念

三个原则决定一切排版决策：

1. **手机上刷得动。** 每屏必须有视觉锚点（色彩、形状、大小对比），不能让读者在纯文字里迷失。段落不超过 4 行，表格不超过 5 列。
2. **扫读友好。** 读者先扫标题、加粗词、数字、彩色标签，再决定细不细读。关键信息必须「跳出来」。
3. **像杂志，不像公文。** 用卡片、色块、左边框、大引号制造节奏变化。拒绝纯文字堆砌。

## 品牌设计令牌

来自 [[brand-social-card-standards]]：

| 令牌 | 值 | 用途 |
|------|-----|------|
| 深靛蓝 | `#1700AC` | 主品牌色、封面底、标题左边框、CTA 底 |
| 柠绿 | `#D9FEA9` | 高亮、大字报背景、封面装饰条 |
| 翠绿 | `#00BE62` | 正确/正面/路径 A 标签 |
| 红色 | `#C90000` | 风险/警告/路径 B 标签、警告左边框 |
| 纸白 | `#fafaf8` | 卡片底色 |
| 墨黑 | `#0a0a0a` | 正文 |

**字体**：正文 `Noto Serif SC`（杂志感），无衬线 `Noto Sans SC`（标签/数字），等宽 `IBM Plex Mono`（标注/数据）。正文 17px，行高 1.75。

## 组件目录

以下组件构成排版语言。参考 `references/components-reference.md` 获取完整 HTML 片段。

### 封面卡片 (Cover Card)
靛蓝满版底 + 白字标题 + 柠绿装饰条。可选眉头标签、副标题。用于文章顶部第一屏。

### 章节头 (Chapter Header)
章节编号（小号无衬线大写）+ 大标题 + 可选副标题。章节之间用细线或浅色背景区分。

### 警告卡 (Warning Card)
浅红底 `#fff5f5` + 红色 `#C90000` 4px 左边框 + 圆角右侧。用于风险提示、法律红线、骗局警示。

### 信息卡 (Info Card)
浅紫底 `#f6f4ff` + 靛蓝 `#1700AC` 4px 左边框 + 圆角右侧。用于补充说明、背景信息、温和提醒。

### 数据表 (Data Table)
上下粗线（2px `#000`）+ 行间细线（1px `#ddd`）。表头加粗居中，首列加粗左对齐。用于费用明细、条件对比。

### 金钱卡组 (Money Cards)
三列 flex 并排，每列不同边框色（绿/靛蓝/红），居中大数字 + 条件说明。用于金额、补偿类型展示。

### 分支流程图 (Branch Flow)
居中提问框（靛蓝底白字）→ 分叉箭头 → 2-3 列并排选择卡。Yes 用绿框、No 用红框、备选用紫框。

### Q&A 块 (QA Block)
问题：靛蓝底白字粗体；答案：浅灰底正文。圆角卡片上下拼接。用于高频疑问集中解答。

### 大字报 (Big Quote)
柠绿 `#D9FEA9` 底 + 靛蓝 `#1700AC` 大号粗体字居中。用于核心观点、一句话总结、行动号召。

### 口诀块 (Mnemonic Block)
靛蓝底白字圆角卡片，关键词柠绿高亮。用于易记的操作要点总结。

### 带编号步骤 (Numbered Steps)
圆形靛蓝数字（44×44px）+ 右侧标题 + 正文/列表。用于操作流程、分步指南。

### 快速对照卡 (Quick Reference Card)
浅灰底卡片，每行：彩色标签（绿/红/靛蓝/灰）+ 主文 + 备注。用于多条信息的快速索引。

### CTA 尾卡 (CTA Footer)
靛蓝底白字大圆角卡片。列出可提供的帮助项（圆角药丸标签），尾部署名 + 公众号名。**必须放在文章末尾。**

### 落款 (Byline)
居中浅灰色小字：组织名 + 口号 + 转发引导。

## 排版规则速查

### 层级节奏
- **一、二、三** 用 `<div class="chapter">` 章节头
- 章节内子标题用左边框 `sub-title`（靛蓝 4px left border）
- 正文段落 `<p>` 不超过 4 行

### 文字处理
- 关键术语首次出现时**加粗**
- 对话/引用用「」而非 "" 
- 破折号用 ——（两个 em-dash）
- 金额、百分比、天数用加粗数字
- 每段开头不要空格缩进

### 间距基准
- 章节上下间距 40px
- 组件上下间距 20-28px
- 卡片内边距 18-20px
- 正文段落间距 8-12px

### 色彩语义
- 靛蓝 = 信息、指引、行动
- 红色 = 风险、警告、禁止
- 绿色 = 正确、合法、可行路径
- 柠绿 = 强调、大字报、封面点缀
- 灰色 = 辅助说明、备注、落款

## 工作流程

### 1. 获取内容
- 用户提供文案草稿或主题
- 确认是否需要先写文案（参考 `[[account-stance-writing-principles]]` 检查立场和调性）
- 如果同时需要社交卡片，参考 `guizang-social-card-skill`

### 2. 规划版面
在脑中或草稿中列出：
```
封面 → 章节1（是什么）→ 章节2（怎么办）→ 章节3（坑在哪）→ CTA
```
每章节分配 1-3 个组件，确保组件类型不重复（不要连续三个警告卡）。

### 3. 构建 HTML
- **从种子模板开始**：复制 `assets/template-wechat-article.html` 到贴文文件夹，重命名为 `index.html`
- 模板已预写全部 15 个组件的 CSS 和完整的 HTML 骨架
- 只需替换 `<!-- ══ 组件 XX · XXX ══ -->` 注释块中的占位内容
- 删掉不需要的组件块，保留需要的
- 不要重写 CSS——模板中的 CSS 是经过实战验证的

### 4. 自检
- [ ] 封面是否有视觉冲击力？
- [ ] 每个章节是否有至少一个非纯文字的视觉组件？
- [ ] 颜色语义是否正确（红=警告、绿=正确、靛蓝=信息）？
- [ ] 段落是否都不超过 4 行？
- [ ] 文末是否有 CTA？
- [ ] CTA 是否指向社团而非政府？
- [ ] 语气是否站在工人这边？

### 5. 交付
- 输出自包含 HTML 文件到对应贴文文件夹
- 同时保存纯文本文案到 `文案.md`（参考 `[[wechat-article-workflow]]`）

## 反模式（不要做）

- ❌ 纯文字从头到尾，没有任何视觉组件
- ❌ 段落超过 5 行不换行
- ❌ 不用表格展示对比/费用/条件类信息
- ❌ CTA 指向第三方（政府热线、外部链接）而非自己的联系渠道
- ❌ 红绿色用于纯装饰（必须承载语义）
- ❌ 封面用白底（必须在首屏制造色彩冲击）
- ❌ 16px 以下的正文字号
- ❌ 重复使用同一组件类型连续 3 次以上
- ❌ 用 emoji 替代彩色标签（emoji 在不同系统显示不一致）

## 参考文件

- `assets/template-wechat-article.html` — **种子模板**。所有 15 个组件 CSS + HTML 骨架已预写。每次排版从这里复制，只替换内容。
- `references/components-reference.md` — 每个组件的完整 HTML/CSS 代码片段（如需手动组合时查阅）
- `references/example-articles.md` — 已完成贴文的组件拆解分析

Related memories: [[brand-social-card-standards]], [[wechat-article-workflow]], [[account-stance-writing-principles]]
