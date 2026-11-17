---
name: pick-ui-library-cn
description: 中文前端任务查找精选库。Pick the library for a frontend task from a curated list — primitives, toasts, drawers, command menus, OTP, numbers, charts, virtualization, drag and drop, state, styling.
---

# Picking The Right Library

## Initial Response

When this skill is first invoked without a specific question, respond only with:

> 我可以按你的前端任务查找合适的库；这份独立中文适配沿用 Emil Kowalski 的精选清单。

Do not provide any other information until the user asks a question.

A lookup skill. When invoked with a task ("I need toasts", "what should I use for drag and drop?"), match the task to the curated list below and recommend the library. These are deliberate, taste-driven picks — don't substitute alternatives outside this list unless the user asks for one or the task genuinely isn't covered.

## How to use this

1. **Identify the task**, not the library the user named. "I need to show a dropdown" is a UI-primitives task (base-ui), even if they asked about something else.
2. **Check what's already installed.** Look at `package.json` first. If the project already uses a listed library, use it. If it uses a competitor (e.g. react-window instead of Virtuoso), flag the recommendation but don't churn the dependency without being asked.
3. **Recommend one library**, state what it's for in one sentence, and install/wire it up if that's part of the request. Don't present a menu of options when the list has a clear answer.
4. If the task isn't covered by the list, say so explicitly and recommend from your own knowledge — but be clear you've left the curated list.

## The list

### UI components & primitives

| Task | Library |
| --- | --- |
| Unstyled, accessible UI components (dialogs, popovers, menus, selects…) | [base-ui](https://base-ui.com) |
| Command menus (⌘K palettes) | [cmdk](https://cmdk.paco.me) |
| Toasts / notifications | [Sonner](https://sonner.emilkowal.ski) |
| Drawers / bottom sheets | [Vaul](https://vaul.emilkowal.ski) |
| One-time password / verification code inputs | [input-otp](https://input-otp.rodz.dev) |
| Customizable GUIs / control panels | [Leva](https://github.com/pmndrs/leva) |

### Motion & visuals

| Task | Library |
| --- | --- |
| General-purpose animation (springs, layout animations, enter/exit) | [motion](https://motion.dev) (Framer Motion) |
| Animating numbers (counters, prices, stats) | [NumberFlow](https://number-flow.barvian.me) |
| Animated text components | [torph](https://torph.lochie.me/) |
| 3D globes | [Cobe](https://cobe.vercel.app) |
| Dynamic OG images (HTML/CSS → SVG) | [Satori](https://github.com/vercel/satori) |
| Syntax highlighting | [shiki](https://shiki.style) |

Reach for motion when you need springs, layout animations, exit animations, or gesture-driven values. A simple hover or fade doesn't need it — plain CSS transitions are the right tool there.

### Charts

| Task | Library |
| --- | --- |
| Real-time / streaming charts | [Liveline](https://github.com/benjitaylor/liveline) |
| General charts (static or interactive dashboards) | [recharts](https://recharts.org) |

The split: if data points arrive live and the chart scrolls with time, use Liveline. Everything else is recharts.

### Interaction & performance

| Task | Library |
| --- | --- |
| Drag and drop | [dnd kit](https://dndkit.com) |
| Virtualization (long lists, large tables) | [Virtuoso](https://virtuoso.dev) |

### State & styling

| Task | Library |
| --- | --- |
| State management | [zustand](https://zustand.docs.pmnd.rs) |
| Constructing `className` strings conditionally | [clsx](https://github.com/lukeed/clsx) |
| Type-safe, variant-driven styling for Tailwind | [cva](https://cva.style) |
| Theme switching / dark mode (no flash on load) | [next-themes](https://github.com/pacocoursey/next-themes) |

The styling split: clsx for ad-hoc conditional classes; cva when a component has real variants (size, intent, state) that deserve a typed API. They compose — cva uses clsx-style inputs internally.

## Common mismatches to catch

- **Toasts built by hand or with a modal library** → Sonner exists for exactly this.
- **A `<div>`-based dropdown/dialog with manual focus handling** → base-ui, which handles accessibility, focus trapping, and dismissal.
- **Animating a number by re-rendering text** → NumberFlow handles digit transitions properly.
- **Rendering a 1,000+ row list directly** → Virtuoso before reaching for pagination hacks.
- **A `useState`-per-component web of props for shared state** → zustand.
- **Template-literal className ternaries three conditions deep** → clsx (or cva if it's variant-shaped).


## 中文选库适配 — pick-ui-library-cn 新增

独立非官方适配，沿用上游精选清单及任务匹配方法。它是一份有偏好的清单，不是所有库的客观排行，也不代表原作者对本适配的认可。

### 按中文任务找类别

把“消息提示”对应 toasts，“底部抽屉”对应 drawers / bottom sheets，“快捷命令面板”对应 command menus，“验证码格子”对应 one-time password inputs，“长列表”对应 virtualization。先根据交互意图进入原清单，不按中文关键词机械安装。

用户已经指定某个库、框架或项目约束时先遵从；清单用于补充选择，不能推翻明确要求。先检查 package.json 和锁文件中的现有依赖，不将推荐自动升级为换库或新增运行时。

### 推荐说明保持简短

用中文给出一个匹配项及一句任务理由，保留包名和官方链接原样。说明这是上游清单中的选择；超出清单时明确标出，并按当前项目约束另行核实。版本兼容、维护状态或浏览器支持需查当前官方材料，不能将清单快照称为实时验证结果。

只有用户要求安装或接入时才修改依赖、配置和代码；只问“用什么库”时给建议即可。原流程对简单 hover/fade 使用 CSS、对已有竞争依赖避免擅自迁移的边界继续有效。
