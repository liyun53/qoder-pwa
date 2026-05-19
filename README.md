# QoderWork Mobile PWA

QoderWork 移动端快捷入口 —— 一个具有科技感深色风格的 Progressive Web App（PWA），可以像原生 App 一样添加到手机桌面使用。

## 文件结构

```
qoder-pwa/
├── index.html    # 主页面（含内嵌 CSS/JS）
├── manifest.json # PWA 配置清单
├── sw.js         # Service Worker（离线缓存）
├── icon.svg      # 应用图标
└── README.md     # 使用说明
```

## 如何安装到手机

### Android（Chrome 浏览器）
1. 用 Chrome 打开部署好的网页链接
2. 点击浏览器菜单（右上角 ⋮）
3. 选择「添加到主屏幕」或「安装应用」
4. 桌面会出现「小Q」图标，点击即可全屏运行

### iOS（Safari 浏览器）
1. 用 Safari 打开部署好的网页链接
2. 点击底部分享按钮（□↑）
3. 选择「添加到主屏幕」
4. 桌面会出现「小Q」图标，点击即可全屏运行

## 如何部署

### 方案一：本地预览（最简单）
直接用浏览器打开 `index.html` 文件即可查看效果。PWA 安装功能需要以下方式才能生效。

### 方案二：GitHub Pages（免费）
1. 把这四个文件上传到一个 GitHub 仓库
2. 开启 GitHub Pages（Settings → Pages → 选择分支）
3. 获得 `https://你的用户名.github.io/仓库名/` 链接
4. 手机浏览器打开该链接，按上述步骤安装

### 方案三：Vercel / Netlify（免费）
1. 把这四个文件打包成压缩包
2. 上传到 Vercel 或 Netlify
3. 自动获得 HTTPS 链接，可直接安装

### 方案四：本地局域网访问
如果你有 Python（或其他静态服务器工具）：
```bash
# 进入 qoder-pwa 文件夹后执行
python -m http.server 8080
# 然后手机浏览器访问电脑的局域网IP:8080
```

## 功能说明

当前版本为前端界面框架，包含：
- **首页**：快速对话入口、快捷功能卡片、最近动态
- **功能页**：完整功能列表展示
- **设置页**：PWA 状态检测、缓存清理、安装指引

## 技术特性

- 支持离线访问（Service Worker 缓存）
- 可添加到主屏幕（standalone 全屏模式）
- 深色科技感 UI（玻璃态、霓虹光效、动态网格背景）
- 响应式布局，适配全面屏和安全区
- 单页面应用（SPA），切换流畅

## 扩展建议

如需连接真实后端（比如 QoderWork 的 API），可以在 `index.html` 的交互逻辑中：
1. 将 `showToast('功能开发中')` 替换为实际的 API 调用
2. 添加用户登录状态管理
3. 接入 WebSocket 实现实时对话

## 注意事项

- 图标使用 SVG 格式，现代浏览器均支持。如需兼容旧版 iOS，可将 `icon.svg` 替换为 192x192 和 512x512 的 PNG 图标，并同步修改 `manifest.json` 中的 `icons` 字段。
- PWA 的推送通知、后台同步等高级功能需要额外的服务器配置。
