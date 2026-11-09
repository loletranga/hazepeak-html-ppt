# hazepeak-html-ppt

单文件 HTML 演示文稿(PPT)生成 skill —— 档案编辑风:纸感米白 + 墨黑 + 信号红,高信息密度,无装饰性页眉页脚。

A single-file HTML presentation (deck) skill — archival-editorial style: paper white + ink black + signal red, high information density, no decorative headers or footers.

GitHub:<https://github.com/loletranga/hazepeak-html-ppt>

## 功能 / What it does

- 把决策报告、分析材料、方案比较等内容做成一个可直接放映的单文件 HTML PPT(1280×720 固定画布,任意屏幕等比缩放)。
  Turns decision reports, analyses and option comparisons into a single self-contained HTML deck (1280×720 fixed canvas, scales to any screen).
- 内置 27 个版式组件:封面、目录、分节页、万能表格、时间线、条形预算、路线图、结论行、双栏核对清单等。
  Ships 27 layout components: cover, TOC, dividers, universal table, timeline, budget bars, roadmap, conclusion rows, two-column checklists, etc.
- 交互齐备:键盘/滚轮/触摸翻页,`O` 缩略索引,`F` 全屏,`#页码` 深链,打印直接导出 PDF。
  Full navigation: keyboard/wheel/touch, `O` overview index, `F` fullscreen, `#page` deep links, print to PDF.
- 附带内容写作规则:源文档语言优先、去 AI 腔、数字诚实(待核验数据不编造)、页码引用一致。
  Includes writing rules: prefer source-document wording, no AI-flavored rhetoric, honest numbers (mark unverified data), consistent page references.

## 安装 / Install

克隆到对应 agent 的 skills 目录即可(以 Claude Code 为例):

Clone it into the agent's skills directory (Claude Code shown as an example):

```bash
git clone https://github.com/loletranga/hazepeak-html-ppt.git ~/.claude/skills/hazepeak-html-ppt
```

各 agent 的安装位置 / Where to install per agent:

| Agent | 个人级(全局)/ Personal | 项目级 / Project |
|---|---|---|
| Claude Code | `~/.claude/skills/hazepeak-html-ppt` | `<项目>/.claude/skills/hazepeak-html-ppt` |
| ZCode | `~/.zcode/skills/hazepeak-html-ppt` | `<项目>/.zcode/skills/hazepeak-html-ppt` |
| Codex / dsh 等其他 agent | 无原生 skills 目录时,克隆到任意路径,并在其指令文件(如 `AGENTS.md`)中写明:制作 HTML PPT 前先读 `<路径>/SKILL.md` / If no native skills dir, clone anywhere and reference `<path>/SKILL.md` from its instruction file (e.g. `AGENTS.md`) | 同左 / Same |

凡支持 SKILL.md(Agent Skills)规范的 agent,克隆到其 skills 目录即可被自动发现;新会话生效。
Any agent that supports the SKILL.md (Agent Skills) convention auto-discovers it after cloning into its skills directory; takes effect in a new session.

## 使用 / Usage

安装后,对话中直接提出 PPT 需求即可触发,例如:
Once installed, just describe the deck in conversation, e.g.:

- 「把这份报告做成一个 hazepeak 风格的 HTML PPT」/ "Turn this report into an HTML deck in the hazepeak style"
- 「给这个方案做一份 10 页左右的决策汇报 PPT」/ "Make a ~10-page decision deck for this proposal"

也可以显式点名 skill(如 Claude Code 中输入 `/hazepeak-html-ppt`)。制作流程见 `SKILL.md`:复制 `references/template.html` 为新文件,按组件地图逐页填充;`node --check` 校验内联 JS 后,起本地服务用浏览器抽查渲染即可交付。
Or invoke the skill explicitly (e.g. `/hazepeak-html-ppt` in Claude Code). Build workflow in `SKILL.md`: copy `references/template.html` and fill pages per the component map; verify the inline JS with `node --check`, spot-check rendering over a local HTTP server, then deliver.

## 文件 / Files

| 文件 / File | 说明 / Description |
|---|---|
| `SKILL.md` | Skill 定义:风格红线、组件地图、写作规则、制作与验证流程 / Skill definition: style rules, component map, writing rules, build & verify workflow |
| `references/hazepeak-ppt.css` | 完整设计系统(约 450 行,带令牌注释) / Full design system (~450 lines, commented tokens) |
| `references/template.html` | 可直接复制的完整骨架(CSS+JS+示例页),已验证渲染 / Copy-paste ready skeleton (CSS+JS+sample slides), render-tested |

放置于 agent 公共 skill 目录(如 `~/.zcode/skills/hazepeak-html-ppt/`)即可被自动发现;本目录(`~/www/_skills/hazepeak-html-ppt/`)为母本。
Place it in the agent's public skills directory (e.g. `~/.zcode/skills/hazepeak-html-ppt/`) for auto-discovery; this directory (`~/www/_skills/hazepeak-html-ppt/`) is the master copy.
