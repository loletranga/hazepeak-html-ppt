# hazepeak-html-ppt

单文件 HTML 演示文稿(PPT)生成 skill —— 档案编辑风:纸感米白 + 墨黑 + 信号红,高信息密度,无装饰性页眉页脚。

A single-file HTML presentation (deck) skill — archival-editorial style: paper white + ink black + signal red, high information density, no decorative headers or footers.

## 功能 / What it does

- 把决策报告、分析材料、方案比较等内容做成一个可直接放映的单文件 HTML PPT(1280×720 固定画布,任意屏幕等比缩放)。
  Turns decision reports, analyses and option comparisons into a single self-contained HTML deck (1280×720 fixed canvas, scales to any screen).
- 内置 27 个版式组件:封面、目录、分节页、万能表格、时间线、条形预算、路线图、结论行、双栏核对清单等。
  Ships 27 layout components: cover, TOC, dividers, universal table, timeline, budget bars, roadmap, conclusion rows, two-column checklists, etc.
- 交互齐备:键盘/滚轮/触摸翻页,`O` 缩略索引,`F` 全屏,`#页码` 深链,打印直接导出 PDF。
  Full navigation: keyboard/wheel/touch, `O` overview index, `F` fullscreen, `#page` deep links, print to PDF.
- 附带内容写作规则:源文档语言优先、去 AI 腔、数字诚实(待核验数据不编造)、页码引用一致。
  Includes writing rules: prefer source-document wording, no AI-flavored rhetoric, honest numbers (mark unverified data), consistent page references.

## 文件 / Files

| 文件 / File | 说明 / Description |
|---|---|
| `SKILL.md` | Skill 定义:风格红线、组件地图、写作规则、制作与验证流程 / Skill definition: style rules, component map, writing rules, build & verify workflow |
| `references/hazepeak-ppt.css` | 完整设计系统(约 450 行,带令牌注释) / Full design system (~450 lines, commented tokens) |
| `references/template.html` | 可直接复制的完整骨架(CSS+JS+示例页),已验证渲染 / Copy-paste ready skeleton (CSS+JS+sample slides), render-tested |

## 使用 / Usage

把 `references/template.html` 复制为新的 HTML,按 SKILL.md 的组件地图逐页填充;`node --check` 校验内联 JS 后,起本地服务用浏览器抽查渲染即可交付。
Copy `references/template.html` to a new HTML file and fill pages per the component map in SKILL.md; verify the inline JS with `node --check`, spot-check rendering over a local HTTP server, then deliver.

放置于 agent 公共 skill 目录(如 `~/.zcode/skills/hazepeak-html-ppt/`)即可被自动发现;本目录(`~/www/_skills/hazepeak-html-ppt/`)为母本。
Place it in the agent's public skills directory (e.g. `~/.zcode/skills/hazepeak-html-ppt/`) for auto-discovery; this directory (`~/www/_skills/hazepeak-html-ppt/`) is the master copy.
