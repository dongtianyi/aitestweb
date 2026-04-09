# Roodle 官方网站

🏃 好用的跑步分析 App

## 技术栈

- **框架**: Vue 3 + TypeScript
- **构建工具**: Vite
- **样式**: SCSS
- **部署**: GitHub Pages / Vercel

## 功能特性

- ✅ 深色主题设计
- ✅ 响应式布局
- ✅ 流畅动画效果
- ✅ 单页滚动展示
- ✅ 移动端适配

## 开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 预览生产构建
npm run preview
```

## 项目结构

```
aitestweb/
├── src/
│   ├── components/
│   │   ├── Navbar.vue       # 导航栏
│   │   ├── Hero.vue         # 首屏 Hero
│   │   ├── Features.vue     # 功能展示
│   │   ├── Advantages.vue   # 产品优势
│   │   ├── Download.vue     # 下载引导
│   │   └── Footer.vue       # 页脚
│   ├── styles/
│   │   ├── variables.scss   # 设计变量
│   │   └── global.scss      # 全局样式
│   ├── App.vue
│   └── main.ts
├── index.html
└── package.json
```

## 设计系统

### 配色

- **主色**: 荧光绿 `#7FFF00`
- **品牌色**: Logo 红 `#E31937`
- **背景**: 纯黑 `#000000` / 深灰 `#0D0D0D`

### 字体

- 中文：思源黑体 / Noto Sans SC
- 英文：System Fonts

## 部署

### GitHub Pages

```bash
npm run build
# 部署 dist 目录到 gh-pages 分支
```

### Vercel

```bash
npm install -g vercel
vercel
```

## License

© 2026 北京北南国信息科技有限公司
