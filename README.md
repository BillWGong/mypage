# BillW's personal page

Vue 3 + Vite 个人主页。保留 Spectral 衬线字体、简洁排版及明暗配色，支持跟随系统或手动选择主题。

## 本地开发

Node.js `^22.18.0` 或 `>=24.12.0`。

```sh
npm install
npm run dev
```

## 构建与预览

```sh
npm run build
npm run preview
```

构建结果位于 `dist/`。生产环境部署该目录，不能直接发布源码根目录或双击 `index.html`。

## 修改内容

- `src/App.vue`：个人介绍、项目、近况、联系方式；项目列表在 `projects` 数组中，`featured: true` 为主推项目。
- `src/style.css`：主题颜色、字体、布局和响应式样式。
- `src/components/ThemeSwitcher.vue`：主题选择及本地保存。
- `avatar.jpg`：原始头像；页面实际加载 `avatar-152.jpg` / `avatar-304.jpg`（按 1x/2x 裁切压缩，源图变更后需重新生成）。
- `public/og.png`：1200×630 社交预览图（Open Graph / Twitter Card）。
- `vercel.json`：静态资源长缓存与基础安全响应头。

## 部署

线上站点 <https://www.billw.top> 由 Vercel 托管，仓库关联 `main` 分支。推送到 `main` 后 Vercel 会自动执行 `npm run build` 并发布 `dist/`。

其他托管平台默认使用根路径 `/`；部署在子路径时通过 `VITE_BASE_PATH=/your-path/ npm run build` 指定。

仓库不再包含 GitHub Pages 工作流（该仓库未启用 Pages）。若以后想改用 GitHub Pages，需要在 **Settings → Pages → Source** 选择 **GitHub Actions**，并重新添加构建发布工作流。
