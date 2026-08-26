# 华中农业大学 · 学习笔记

一个基于 GitHub Pages 托管的静态学习笔记网站，使用纯 HTML/CSS/JavaScript，无任何构建步骤。

## 在线访问

部署后访问地址：`https://<你的用户名>.github.io/<仓库名>/`

## 功能特性

- 搜索：按标题、标签、正文内容模糊搜索
- 标签筛选：点击标签快速过滤笔记
- 阅读弹窗：点击卡片查看笔记全文
- 自动刷新：每 5 分钟自动检查 `notes.json` 更新

## 项目结构

```
├── index.html   # 网站主页面（含全部样式与逻辑）
├── notes.json   # 笔记数据（所有内容都写在这里）
└── README.md
```

## 如何更新笔记

所有内容都存放在 `notes.json` 中，数据结构如下：

```json
{
  "title": "站点标题",
  "subtitle": "副标题（页首横幅文字）",
  "updated": "2026-08-27",
  "notes": [
    {
      "title": "笔记标题",
      "date": "2026-08-25",
      "tags": ["标签1", "标签2"],
      "summary": "卡片上显示的简介",
      "content": "正文内容，支持换行"
    }
  ]
}
```

修改 `notes.json` 后执行以下命令提交推送即可，网站会自动生效：

```bash
git add notes.json
git commit -m "更新笔记"
git push
```

## 本地预览

由于浏览器 `fetch` 读取本地 JSON 有跨域限制，建议用本地服务器预览：

```bash
# Python 3
python -m http.server 8000
```

然后浏览器打开 `http://localhost:8000`

## 部署步骤（首次）

1. 在 GitHub 新建一个仓库（建议 Public）。
2. 将本目录文件推送到仓库：
   ```bash
   git init
   git add .
   git commit -m "initial commit"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/<仓库名>.git
   git push -u origin main
   ```
3. 进入仓库 `Settings → Pages`，Source 选择 `Deploy from a branch`，Branch 选择 `main`，目录 `/ (root)`，点击 Save。
4. 等待 1-2 分钟后访问页面即可。

## 说明

- 网站是纯静态页面，无需后端，适合个人学习笔记展示。
- 若笔记较多，建议先本地用脚本校验 `notes.json` 的 JSON 格式后再推送。
