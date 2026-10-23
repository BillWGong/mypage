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

- `src/App.vue`：个人介绍、项目、近况、联系方式。
- `src/style.css`：主题颜色、字体、布局和响应式样式。
- `src/components/ThemeSwitcher.vue`：主题选择及本地保存。
- `avatar.jpg`：页面使用的原始头像，由 Vite 打包并按原图比例显示。

## GitHub Pages

仓库已附带 `.github/workflows/deploy.yml`。首次发布前，在 GitHub 仓库 **Settings → Pages → Source** 选择 **GitHub Actions**。推送到 `main` 后会自动构建并发布。

工作流使用 Pages 返回的 `base_path`，同时支持项目路径 `/mypage/` 和已配置的自定义域名。其他托管平台默认使用 `/`；有子路径时通过 `VITE_BASE_PATH=/your-path/ npm run build` 指定。

仅迁移代码不会自动更改 GitHub 上的 Pages 设置。
