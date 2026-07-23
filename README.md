# 阅读札记 / Reader

[中文](#中文) · [English](#english)

---

## 中文

一个纯前端、零依赖、单文件的 HTML 阅读器，适合长时间收集和阅读文章。护眼配色、排版舒适、支持添加/编辑/删除文章、多字体多主题、全屏沉浸阅读。

打开即用，无需安装、无需后端、无需联网。

### 特性

- **纯单文件**：整个阅读器只有一个 `reader.html`，双击即用
- **文章管理**：在网页内添加、编辑、删除文章，所有改动自动保存到浏览器本地
- **护眼主题**：护眼底（米黄纸张）、夜间（暖黑）、iOS 暗色（深灰 + 系统蓝），默认 iOS 暗色
- **字体切换**：中文（宋体 / 微软雅黑 / 苹方 / 华文细黑）、英文（Times New Roman / Arial / Helvetica），默认宋体
- **字号调节**：A- / A+ 调节，一键复位
- **全屏阅读**：隐藏侧边栏，充分利用屏幕宽度，工具栏自动收起
- **搜索筛选**：按标题、作者、标签即时筛选
- **键盘导航**：← / → 翻篇，F 切换全屏，Esc 退出
- **响应式**：手机端侧边栏可折叠
- **数据迁移**：导出 JSON 备份，跨机器导入恢复

### 快速开始

1. 下载 `reader.html`
2. 用浏览器打开（推荐 Chrome / Edge / Safari）
3. 点侧边栏「＋ 添加文章」开始收录你的文章

### 文章管理

**添加文章**：点侧边栏「＋ 添加文章」，填写标题、作者、来源、日期、标签、正文。

正文支持简易格式（无需懂 HTML）：

```
## 二级标题
### 三级标题
> 引用文字
- 无序列表项
1. 有序列表项
**加粗**  *斜体*  `代码`
普通段落之间空一行
```

**编辑 / 删除**：每篇文章正文下方有「✎ 编辑」和「🗑 删除」按钮。

- 内置示例文章：编辑/删除记录在本地，源码不动，清除浏览器数据可恢复
- 自定义文章：直接增删，删除后无法找回（请及时导出备份）

### 数据备份与迁移

文章保存在浏览器 `localStorage`，绑定在「当前机器 + 当前浏览器」。换机器、换浏览器或清除浏览数据会丢失，请定期导出备份。

| 操作 | 说明 |
|------|------|
| ⬇ 导出备份 | 侧边栏点「导出备份」，下载 `reader-backup-日期.json` |
| ⬆ 导入 | 侧边栏点「导入」，选择之前的 JSON 备份文件 |

导入时按文章 ID 智能合并：相同文章被导入版本覆盖，本机独有文章保留不丢失。

**建议**：把导出的 JSON 备份也存到网盘或 Git 仓库，等于云端存了一份，任何机器下载 + 导入即可恢复。

### 主题

| 主题 | 风格 | 默认 |
|------|------|------|
| 护眼底 | 米黄纸张感 | |
| 夜间 | 暖黑底 + 金强调 | |
| iOS 暗色 | 深灰底 + iOS 系统蓝 | ✓ |

主题选择保存在本地，下次打开自动恢复。

### 键盘快捷键

| 按键 | 功能 |
|------|------|
| ← | 上一篇 |
| → | 下一篇 |
| F | 切换全屏阅读 |
| Esc | 退出全屏 / 关闭弹窗 |

### 在源码中直接添加文章（可选）

编辑 `reader.html`，找到 `ARTICLES` 数组（搜索 `const ARTICLES`），按下面格式追加：

```javascript
{
  id: "20260724-1",            // 唯一编号
  title: "文章标题",
  author: "作者",              // 可留空 ""
  source: "来源",              // 可留空 ""
  date: "2026-07-24",
  tags: ["标签1", "标签2"],
  content: `
    <p>正文用 HTML 书写……</p>
    <h2>小标题</h2>
    <blockquote>引用</blockquote>
  `
}
```

网页内添加和源码添加两种方式可并存。

### 技术说明

- 纯 HTML + CSS + 原生 JavaScript，无任何框架、无构建步骤
- 字体使用系统字体，离线可用
- 数据存储使用浏览器 `localStorage`
- 兼容现代浏览器（Chrome / Edge / Safari / Firefox）

---

## English

A zero-dependency, single-file HTML reader for collecting and reading articles over the long term. Eye-friendly themes, comfortable typography, article add/edit/delete, multiple fonts and themes, and fullscreen immersive reading.

Just open and use — no install, no backend, no internet required.

### Features

- **Single file**: the entire reader is one `reader.html`, double-click to run
- **Article management**: add, edit, delete articles in-page; all changes auto-saved to browser storage
- **Eye-friendly themes**: Paper (warm cream), Night (warm dark), iOS Dark (deep gray + system blue); iOS Dark by default
- **Font switching**: Chinese (Songti / Microsoft YaHei / PingFang / STXihei), English (Times New Roman / Arial / Helvetica); Songti by default
- **Font size**: A- / A+ adjustment, one-click reset
- **Fullscreen reading**: hides sidebar, uses full screen width, auto-collapsing toolbar
- **Search & filter**: instant filter by title, author, or tag
- **Keyboard navigation**: ← / → to switch articles, F to toggle fullscreen, Esc to exit
- **Responsive**: collapsible sidebar on mobile
- **Data migration**: export JSON backup, import on another machine

### Quick Start

1. Download `reader.html`
2. Open it in a browser (Chrome / Edge / Safari recommended)
3. Click "＋ 添加文章" (Add Article) in the sidebar to start collecting

### Article Management

**Add article**: Click "＋ 添加文章" in the sidebar. Fill in title, author, source, date, tags, and body.

The body supports a lightweight markdown-like syntax (no HTML knowledge required):

```
## Heading 2
### Heading 3
> Quote
- Unordered list item
1. Ordered list item
**Bold**  *Italic*  `Code`
Separate paragraphs with a blank line
```

**Edit / Delete**: Each article has "✎ 编辑" (Edit) and "🗑 删除" (Delete) buttons below its body.

- Built-in sample articles: edits/deletes are recorded locally; source code is untouched, clearing browser data restores them
- Custom articles: added/deleted directly; deletions cannot be undone (export a backup in time)

### Data Backup & Migration

Articles are stored in the browser's `localStorage`, bound to "this machine + this browser". Changing machines, switching browsers, or clearing browser data will lose them — please export backups regularly.

| Action | Description |
|--------|-------------|
| ⬇ Export backup | Click "导出备份" in the sidebar to download `reader-backup-YYYYMMDD.json` |
| ⬆ Import | Click "导入" in the sidebar and select a previous JSON backup |

Importing merges by article ID: identical articles are overwritten by the imported version; locally-unique articles are preserved.

**Tip**: Also store the exported JSON backup in cloud storage or a Git repo — then any machine can download + import to restore.

### Themes

| Theme | Style | Default |
|-------|-------|---------|
| Paper (护眼底) | Warm cream paper | |
| Night (夜间) | Warm dark + gold accent | |
| iOS Dark (iOS 暗色) | Deep gray + iOS system blue | ✓ |

Theme choice is saved locally and restored on next open.

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| ← | Previous article |
| → | Next article |
| F | Toggle fullscreen reading |
| Esc | Exit fullscreen / close dialog |

### Adding Articles in Source Code (Optional)

Edit `reader.html`, find the `ARTICLES` array (search for `const ARTICLES`), and append in this format:

```javascript
{
  id: "20260724-1",            // unique id
  title: "Article Title",
  author: "Author",            // can be ""
  source: "Source",            // can be ""
  date: "2026-07-24",
  tags: ["tag1", "tag2"],
  content: `
    <p>Body in HTML...</p>
    <h2>Subheading</h2>
    <blockquote>Quote</blockquote>
  `
}
```

In-page adding and source-code adding can coexist.

### Technical Notes

- Pure HTML + CSS + vanilla JavaScript; no frameworks, no build step
- Uses system fonts, works offline
- Data stored in browser `localStorage`
- Compatible with modern browsers (Chrome / Edge / Safari / Firefox)

---

## License

MIT
