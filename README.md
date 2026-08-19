# 浙大戏剧影视 336 学习台

一个无框架、可离线、数据仅保存在浏览器本地的独立学习网页。桌面端采用固定侧栏布局，手机端自动切换为抽屉导航。

## 本地运行

必须通过 HTTP 服务打开，PWA 安装和离线缓存才会生效：

```powershell
python -m http.server 4173
```

访问 `http://127.0.0.1:4173/index.html`。直接双击 `index.html` 仍可使用大部分学习功能，但不能注册离线缓存。

## 数据说明

- 学习计划、历史记录、资讯、素材、题库、草稿、批注、收藏和计时配置保存在浏览器 `localStorage`。
- “错题 & 收藏夹”中的“导出数据”可生成完整 JSON 备份。
- 清除该站点的浏览器数据会删除本地记录；更换设备前请先导出备份。

## 公网部署

项目没有构建步骤，四个运行文件均需放在站点根目录：

- `index.html`
- `manifest.webmanifest`
- `sw.js`
- `app-icon.svg`

仓库已包含 GitHub Pages 工作流。推送到 GitHub 后，在仓库 **Settings → Pages → Source** 中选择 **GitHub Actions**，后续推送会自动更新站点。也可以把整个目录直接上传至 Vercel、Netlify 或 Cloudflare Pages。

公网必须使用 HTTPS，浏览器才会显示“安装应用”入口。
