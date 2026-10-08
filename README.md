# Ufirst Mentor Desk · Ufirst 导师工作台

A single-file, offline-capable "office desk" workbench for the **Ufirst Club** class mentor
(course name: *Nature & Human Spirit* / 自然与人文精神), covering Monday theory sessions
and Saturday field practice, student support and faculty liaison.

为 **Ufirst Club** 班级 mentor 打造的单文件「办公桌」工作台，围绕周一理论课 + 周六实践课、
学生支持与教授联络三条线组织，双击即可离线使用。

---

## 两个语言版本 · Two language versions

| 文件 / File | 语言 / Language | 说明 |
| --- | --- | --- |
| `index.html` | 中文 | 主版本，日常使用 |
| `index-en.html` | English | 给外教 / 国际同事，内容与中文版一一对应 |

两版**共用同一份浏览器数据**（`localStorage` key: `ufirst_workbench_v2`）：
在同一台电脑的同一浏览器里，任何一个版本里做的改动，另一个版本都同步可见。
右下角有小胶囊可一键切换语言。

Both versions read and write the **same browser data store**, so edits made in one
version appear in the other on the same machine. A small pill in the bottom-right
corner switches the language.

---

## 功能 · Features

- **资源库标题行**：团建游戏库 / 外出实践 / 周一理论角 / 活动照片墙，全部折叠为一行，点击展开，可随时新增自定义库。
  Collapsible resource libraries — team-building games, field trips, Monday theory, photo wall — plus custom libraries.
- **团建游戏库**分三阶段：破冰 · 互相认识 / 热身 · 提神 / 团队建设，每页独立滚动，封面取自 mentor 手册原图。
  Game library in three stages: Icebreakers / Energizers / Teambuilding, with cover images from the mentor handbook.
- **本周任务框**：当周全部任务（游戏 / 理论课 / 户外课 / 临时事项）统一收纳，支持拖拽、点 ＋ 或直接打字添加，可一键复制清单发群。
  This week's task tray — everything for the current week in one place; drag, tap ＋, or type directly; one-click copy for the group chat.
- **抽屉式按周扩展**：一周一个抽屉，随时新增，学期内不受限。
  Drawer per week, add as many as the semester needs.
- **数据交接**：导出 / 导入 JSON，下一任 mentor 可完整继承。
  Export / import JSON for handover to the next mentor.

## 移动端 · Mobile

竖向上下滑动 = 浏览页面；只有**横向拖动**才会触发拖拽。手机上添加活动建议直接点卡片右上角的 **＋**。

Swipe up/down to browse — only a **sideways** drag picks up a card. On phones, tapping **＋** on a card is the fastest way to add it.

---

## 数据说明 · About the data

- 活动封面图已 **base64 内嵌**进 HTML，两个页面都是真正的单文件，转发 / 部署不会裂图。
  Cover images are embedded as base64, so each page is genuinely self-contained.
- 你在页面上添加的内容（照片墙照片、各周任务、理论角填写的文字）保存在**浏览器本地 `localStorage`**，
  **不随文件或仓库传播**。换电脑 / 换浏览器 / 交接给他人，请先用页面内的「导出数据」生成 JSON。
  Anything you add in the UI lives in the browser's `localStorage` — it is **not** part of this repo.
  Use the built-in "Export Data" for backup and handover.
- `assets/cards/` 是封面图的源文件（非压缩原件），保留用于后续替换或重新生成页面。
  `assets/cards/` holds the source cover images for future regeneration.

## 部署 · Deployment

纯静态站点，无构建步骤，无依赖。可直接部署到任意静态托管：

- **Cloudflare Pages**：连接本仓库 → Framework preset 选 `None` → Build command 留空 → Build output directory 填 `/` → Deploy。
- **GitHub Pages**：Settings → Pages → Source 选 `Deploy from a branch` → 分支 `main` / 目录 `/ (root)`。
- 本地使用：直接双击 `index.html`。

No build step, no dependencies — plain static files.

## 维护 · Maintenance

- 新增活动：编辑脚本顶部的 `GAME_LIBRARY` / `TRIP_LIBRARY` 数组。
- 修改封面：替换 `assets/cards/g*.jpg`，并对 HTML 内的 base64 做一次同步更新。
- 两个语言版本需**同步修改**，界面文案分别位于各自文件的 `<script>` 与 HTML 结构中。
