# 学术个人主页：零基础使用指南

这是无需安装软件、无需编程、无需构建的静态网站。中文占位内容均需按实际情况修改，不含真实论文或个人资料。

## 1. 在电脑上预览

把 index.html 和 styles.css 放在同一个文件夹，双击 index.html 即可用浏览器打开。修改并保存后，刷新浏览器即可看到变化。README.md 是说明文档，不会显示在主页正文里。

## 2. 创建 GitHub 仓库

1. 打开 https://github.com ，注册或登录，按提示验证邮箱。
2. 点击右上角头像 → Your profile，确认你的 GitHub 用户名（不是个人显示名称）。
3. 本文所有 `USERNAME` 都是占位符，必须替换成你自己的用户名，不要直接照抄。
4. 点击右上角 `+` → `New repository`。
5. Repository name 填写 `USERNAME.github.io`。例如，若用户名为 `example-researcher`，仓库名就是 `example-researcher.github.io`（仅为举例）。不要加入 https:// 或斜杠。
6. 选择 `Public`（公开），勾选 `Add a README file`，点击 `Create repository`。网站及上传的内容将公开，请只使用你愿意公开的联系方式。
7. 如果同名仓库已经存在，打开现有仓库并备份原文件，再更新需要的文件，不必新建。

## 3. 上传文件

1. 在仓库的 `Code` 页点击 `Add file` → `Upload files`。
2. 将本套文件中的 index.html、styles.css、README.md 拖入上传区域。README.md 可替换自动生成的说明。
3. 确认 index.html 和 styles.css 直接位于仓库最外层，不要上传包含它们的整个文件夹，也不要只上传 ZIP。
4. 在提交说明填写“添加学术主页”，点击 `Commit changes`，保存到 main 分支。

仓库最外层应该是：

```text
USERNAME.github.io/
├── index.html
├── styles.css
└── README.md
```

## 4. 启用 GitHub Pages

1. 在仓库顶部点击 `Settings`，左侧点击 `Pages`。
2. 在 `Build and deployment` 下，将 `Source` 设为 `Deploy from a branch`。
3. 在 `Branch` 选择 `main`，文件夹选择 `/(root)`，点击 `Save`。如果已是这些设置，则保持即可。
4. 等待部署，通常几分钟，首次发布可能需要约 10 分钟。可查看仓库 `Actions` 中的 `pages build and deployment` 状态。
5. 返回 `Settings → Pages`，看到网站地址后点击 `Visit site`。你的主页地址是 `https://USERNAME.github.io/`，其中 USERNAME 要替换为真实用户名。

官方说明：https://docs.github.com/en/pages/quickstart

## 5. 不懂 HTML 也能修改

在 GitHub 仓库中点击 index.html，再点击铅笔图标（Edit this file）。找到要改的中文，替换文字，保留周围 `<p>`、`</p>` 等标签。完成后点击 `Commit changes`。每次保存后 Pages 都会重新部署，等待完成后刷新网站。

建议按顺序修改：

- 浏览器标题：`你的姓名 · 学术主页`；同时更新 description 中的摘要。
- 左侧资料：你的姓名、Your Name、你的身份、你的院系和大学。
- 关于我：教育背景、当前工作、研究主题。
- 研究兴趣：三个方向的标题和说明，可按需删减整个 `<li>…</li>`。
- 笔记与项目：替换示例内容。添加条目可复制完整的 `<article class="entry">…</article>`。
- 论文发表：填写真实论文、作者、会议或期刊、年份和发表状态；未发表论文时，将示例 article 整段删除，保留一句“目前暂无公开论文，研究进行中”。
- 邮箱：搜索 `your.name@example.com`，两处都改成你的邮箱（包含 mailto: 后的一处）。
- 页尾：替换“你的姓名”。全部修改后搜索“你的”“示例”“待补充”“Your Name”，检查有无遗漏。

### 添加真实链接

需要给论文、项目或学术档案加链接时，可将下面这行放在相应条目的结束标签前，并换成真实网址和文字：

```html
<p><a href="https://example.com">论文全文 / 项目代码</a></p>
```

上面的 example.com 是格式示例，必须替换。暂时没有链接时保留普通文字即可。不要把本机 C:\ 开头的路径当成网站链接。

### 添加头像（可选）

将你自己的照片命名为 photo.jpg，上传到仓库最外层，在 index.html 的 `<h1>` 前添加：

```html
<img src="photo.jpg" alt="你的姓名的个人照片" width="120" height="120" style="object-fit:cover;border-radius:50%;">
```

### 修改配色（可选）

打开 styles.css，第一行的 `--accent:#426958` 是绿色强调色；可以换成 `#345b86`（蓝色）。不需要改样式也能直接使用。

## 6. 常见问题

- **404**：核对仓库是否准确命名为你的用户名.github.io；核对 main / (root)；确认文件名是小写 index.html 且在最外层；检查 Actions 是否部署完成。
- **样式没有加载**：确认 styles.css 与 index.html 同级、文件名大小写一致；Windows 请打开“显示文件扩展名”，避免保存成 styles.css.txt 或 index.html.txt。
- **修改后没变化**：确认已经 Commit changes，等待 Actions 完成，再按 Ctrl+F5 强制刷新。
- **中文乱码**：本套文件采用 UTF-8；本地编辑时选择 UTF-8 编码保存。
- **没有 main 可选**：先完成第一次文件提交，再返回 Pages 设置。
- **找不到 Settings / 无法保存**：确认你登录的是仓库拥有者账号。

## 文件与功能

index.html 管理内容；styles.css 管理外观；README.md 提供说明。布局适配手机，支持键盘导航与打印，无第三方字体、脚本或追踪服务。联系邮箱链接需要访问者设备上配置邮件应用。本网站不含后台、登录或表单。
