# 蜜学热榜 - 部署说明

## 一键部署到 Vercel（推荐）

1. 把这个文件夹推到你自己的 GitHub 仓库：

```bash
# 在 hot-site 目录下
git init
git add .
git commit -m "init: 蜜学热榜全球热点聚合站"
git branch -M main
git remote add origin https://github.com/你的用户名/mihoc-hot.git
git push -u origin main
```

2. 打开 [vercel.com](https://vercel.com)，用 GitHub 登录

3. 点击 **New Project** → 导入你的 `mihoc-hot` 仓库

4. 直接点 **Deploy**（无需任何配置，vercel.json 已配好）

5. 获得网址：`https://mihoc-hot.vercel.app` ✅

## 定时更新

推送到 GitHub 后，`.github/workflows/collect.yml` 会自动每小时运行一次，抓取最新热点数据并提交到仓库。Vercel 检测到仓库更新后自动重新部署。

## 本地预览

```bash
cd hot-site
python -m http.server 8080
# 打开 http://localhost:8080
```

## 自定义

- 修改 `index.html` 中的 CSS 变量可换主题色
- 修改 `.github/workflows/collect.yml` 中的 `GLOBAL` 数组可增减数据源
