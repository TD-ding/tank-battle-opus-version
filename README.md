# 坦克大战 · Tank Battle (opus-version)

一个零依赖、单文件的 HTML5 Canvas 坦克大战小游戏。用纯原生 JavaScript 编写，双击即玩。

![tech](https://img.shields.io/badge/HTML5-Canvas-orange) ![deps](https://img.shields.io/badge/dependencies-0-brightgreen) ![license](https://img.shields.io/badge/license-MIT-blue)

## 特性

- 🎮 经典坦克大战玩法：移动、开火、守护基地、逐关推进
- 🧱 网格地图与多种地形：砖墙（可破坏）、钢墙（不可破坏）、草丛（视觉遮蔽）、基地
- 🤖 敌人 AI：向基地寻路 + 随机转向 + 间歇开火，关卡越高越强
- ⭐ 道具系统：火力升级（三连发）、护盾、清屏炸弹
- 🔊 WebAudio 合成音效（无外部资源），可一键开关
- 📱 触屏支持：移动端自带方向盘与开火键
- 💾 本地最高分记录（localStorage）
- ⏸ 暂停 / 失焦 / 切后台自动暂停，防穿墙与防卡键处理

## 快速开始

```bash
python3 -m http.server 8899
# 浏览器访问 http://localhost:8899/tank-battle-opus-version.html
```

或直接用浏览器打开 `tank-battle-opus-version.html`。详见 [docs/deployment.md](docs/deployment.md)。

## 操作

- 移动：方向键 / `WASD`
- 开火：`空格`
- 暂停：`P` / `Esc`
- 音效开关：`M`

## 技术栈

- HTML5 Canvas 2D 渲染
- 原生 JavaScript（ES6 class，IIFE 模块封装）
- 帧率无关的增量时间（delta time）运动
- AABB 碰撞检测 + 网格瓦片碰撞
- WebAudio API 实时合成音效
- localStorage 持久化

无任何第三方依赖，无需构建步骤。

## 项目结构

```
.
├── tank-battle-opus-version.html   # 游戏本体（单文件，含全部逻辑/渲染/样式）
├── docs/
│   └── deployment.md               # 部署与运行指南
├── collab-log.md                   # 协作迭代记录（5 轮）
└── README.md
```

## 开发历程

本项目通过 **5 轮迭代**协作开发完成，每轮聚焦不同主题（初始实现 → 代码质量 → 用户体验 → 功能增强 → Bug 修复），完整记录见 [collab-log.md](collab-log.md)。

## License

MIT
