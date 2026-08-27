# 研究生夏令营 · 学习笔记网站

一个纯 HTML + JSON 的静态网站，记录夏令营（微生物分离与鉴定 / 微生物组数据分析 / 人工智能应用）的学习内容，可直接托管到 GitHub Pages，零成本、免费。

## 文件说明

- `index.html`：网站本体（样式、搜索、阅读弹窗、自动更新逻辑都在里面）
- `notes.json`：你的笔记数据，**以后写笔记只改这个文件**
- `README.md`：本说明

## 部署步骤

1. 在 GitHub 新建一个仓库（Public 免费托管）。
2. 把 `index.html` 和 `notes.json` 上传到仓库根目录。
3. 仓库 `Settings` → `Pages` → Source 选 `main` 分支 `/root` → 保存。
4. 等 1~2 分钟，访问 `https://你的用户名.github.io/仓库名/`。

## 如何添加 / 更新笔记

编辑 `notes.json`，在 `notes` 数组里按同样格式添加一条即可：

```json
{
  "title": "笔记标题",
  "date": "2026-08-27",
  "tags": ["标签1", "标签2"],
  "summary": "卡片上显示的一两句话简介",
  "content": "点击卡片后显示的完整正文，\n可以用换行分段。"
}
```

推送后网站会自动读取最新的 `notes.json`（每 5 分钟自动检查一次，也可点“刷新”立即更新），无需重新部署。

## 本地预览

直接双击 `index.html` 可能因浏览器安全策略无法读取 `notes.json`，推荐任选一种：

- 安装 VS Code 的 Live Server 插件，右键 `index.html` → Open with Live Server
- 或在文件夹里运行 `python -m http.server 8000`，然后访问 http://localhost:8000
