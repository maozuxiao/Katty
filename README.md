# 欢迎来到Katty的资料库

个人博客与文档岛屿，通过 GitHub Contents API 自动列出 `docs/` 下的文档。

## 本地预览

GitHub API 需要 HTTP 环境，直接双击打开 `index.html` 会读取失败：

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

## Markdown 转换工具

打开 `tools/md-to-island.html`（同样需要 HTTP 环境）可以：

- 拖入或选择本地 `.md` 文件（支持多文件），实时预览转换效果
- 编辑标题 / 日期 / 简介，切换是否包含目录、代码复制按钮、返回首页链接
- 导出独立的 HTML 页面，**保存到 `docs/` 下即可被首页自动收录**

导出的页面复用仓库的 `assets/`，因此必须位于仓库的一级子目录（如 `docs/`）中。

### 支持的语法

标题与锚点、加粗 / 斜体 / 删除线 / `==高亮==`、行内代码、链接、**引用式链接**、
图片、嵌套列表、任务清单、嵌套引用、表格（含对齐）、GitHub 警告框、脚注、
**定义列表**、代码块（语言标签 + 复制）、YAML front matter（不渲染，取 `title` / `date` / `description`）。

- **数学公式**：`$...$`、`$$...$$`、`\(...\)`、`\[...\]`。默认以等宽源码降级呈现（完全离线）；
  勾选「数学公式（CDN）」后用 KaTeX 排版。源码里被二次转义的 `\\frac` 会自动归一化。
- **原始 HTML**：`<details>`（内部按 Markdown 继续渲染）、`<kbd>`、`<sub>`、`<sup>`、`<u>`、`<mark>`、
  自定义样式段落等走标签 + 属性白名单放行；`script` / `style` / 非 https 的 `iframe` 一律丢弃。
- **Mermaid**：勾选「Mermaid 图（CDN）」后渲染流程图 / 时序图 / 类图等，未勾选时按代码块展示源码。

## 素材署名

页面使用的字体（Nunito / Noto Sans SC）与图标、背景、海浪等素材来自
[animal-island-ui](https://github.com/guokaigdg/animal-island-ui)，
该项目以 **CC BY-NC 4.0（署名 - 非商用）** 协议发布，本站为个人非商用站点。
