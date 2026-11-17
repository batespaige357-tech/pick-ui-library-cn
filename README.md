# Pick UI Library CN

**说清前端任务，再从精选清单中找库。**

基于 [emilkowalski/skills 的 pick-ui-library](https://github.com/emilkowalski/skills/tree/main/skills/pick-ui-library) 小幅中文适配，独立维护、非官方。

## 保留与补充

保留上游完整清单：组件原语、提示、抽屉、命令面板、验证码输入、动画、图表、虚拟列表、拖拽、状态和样式工具。先查看现有依赖，再按任务推荐一个匹配项。

中文补充解释常见需求对应的类别，尊重项目既有技术和用户指定方案，区分“建议用什么”和“现在安装接入”。原清单有明确偏好，不是通用排行。

## 安装与调用

```bash
npx skills add batespaige357-tech/pick-ui-library-cn --skill pick-ui-library-cn
```

显式告诉助手：“用 pick-ui-library-cn 根据这个需求推荐一个库，先看项目依赖，不要安装。”Codex 可使用 `$pick-ui-library-cn`。需要接入时再明确要求。

手动安装复制 `skills/pick-ui-library-cn` 完整目录。本包保留上游显式调用意图，在支持 openai.yaml 的宿主中关闭隐式调用；其他宿主依其规则。不会捆绑或安装清单中的组件库。

## 来源与验证

MIT，保留 Emil Kowalski 原版权和完整许可证，详见 [CHANGES.md](CHANGES.md)。

已检查原清单保留、调用策略、UTF-8、本地引用和技能格式；未在实际项目评估选库效果、安装依赖、验证组件兼容性或进行助手行为评估。清单快照不是实时维护状态报告。未运行前端编译，不含示例网页、效果截图或前后对比。
