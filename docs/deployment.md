# 部署与运行指南

坦克大战（opus-version）是一个**纯前端单文件**游戏，零依赖、零构建，开箱即用。

## 运行方式

### 方式一：直接双击打开（最简单）

直接用浏览器打开 `tank-battle-opus-version.html` 即可游玩。

> 注意：部分浏览器在 `file://` 协议下对 WebAudio 自动播放策略较严格，首次按键后音效才会启用，属正常现象。

### 方式二：本地静态服务器（推荐）

为获得最佳兼容性（尤其是音效），建议通过 HTTP 服务运行：

```bash
# 在项目根目录执行（Python 3）
python3 -m http.server 8899
```

然后浏览器访问：<http://localhost:8899/tank-battle-opus-version.html>

其他等价方式：

```bash
# Node.js
npx serve .

# PHP
php -S localhost:8899
```

### 方式三：部署到静态托管

把 `tank-battle-opus-version.html` 上传到任意静态托管即可：

- **GitHub Pages**：仓库 Settings → Pages，选择 main 分支根目录，访问 `https://<用户名>.github.io/tank-battle-opus-version/tank-battle-opus-version.html`
- **Vercel / Netlify**：拖拽文件或连接仓库，无需任何构建配置
- **任意 Nginx / 对象存储（OSS/S3）**：作为静态资源直接提供

## 操作说明

| 操作 | 按键 |
|------|------|
| 移动 | 方向键 或 `W` `A` `S` `D` |
| 开火 | `空格` |
| 暂停 / 继续 | `P` 或 `Esc` |
| 音效开关 | `M` |
| 触屏 | 屏幕方向盘 + 开火键（移动端自动可用） |

## 玩法目标

- 摧毁本关所有敌方坦克即可过关，关卡越高敌人越快、越多。
- **守住底部基地（老鹰）**：基地被摧毁立即游戏结束。
- 击毁**闪烁高亮**的敌人会掉落道具：
  - ★ **星星**：火力升级（射速更快 → 三连发）并加分
  - ⛊ **护盾**：短时间免疫敌方子弹
  - ✸ **清屏**：立即摧毁场上所有敌人
- 最高分通过 `localStorage` 本地保存。

## 浏览器兼容性

支持任何实现 HTML5 Canvas 与 WebAudio 的现代浏览器（Chrome / Edge / Firefox / Safari）。无需联网、无外部依赖。

## 运行环境要求

- 无需 Node、无需构建工具、无需安装依赖。
- 仅需一个现代浏览器；可选一个静态文件服务器。
