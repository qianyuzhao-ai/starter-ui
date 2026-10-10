# Starter UI

实验项目的最小设计规范。颜色、字号、间距从第一天起统一成 token，同时支持 Light 和 Dark。项目长大后换品牌色或调整字号，只改 token，不用全局搜索替换。

**在线查看：** https://qianyuzhao-ai.github.io/starter-ui/

## 包含什么

| 文件 | 内容 |
|---|---|
| `index.html` | 完整规范页面：颜色、字体、间距圆角、组件实时预览，可切换 Light / Dark |
| `tailwind/starter-ui.css` | Tailwind v4 配置，复制到项目的 `app.css` 即可使用 |
| `tokens.json` | 全部 token 的原始数据（颜色含两个主题、字号、间距、圆角、阴影） |
| `components/*.md` | Button、Input、Card、Badge 的使用说明和 Tailwind 写法 |

## 快速开始（Tailwind v4）

1. 把 `tailwind/starter-ui.css` 的内容复制到项目的 `app.css`。
2. 在 `<head>` 里加上主题切换脚本，避免页面闪白：

   ```html
   <script>
     const t = localStorage.getItem('theme');
     const dark = t ? t === 'dark' : matchMedia('(prefers-color-scheme: dark)').matches;
     document.documentElement.classList.toggle('dark', dark);
   </script>
   ```

3. 组件里只写语义类：

   ```html
   <div class="bg-surface border border-border rounded-lg p-4">
     <h3 class="text-h3 font-semibold">邀请新成员</h3>
     <p class="text-body text-fg-muted mt-1">成员可以查看和编辑这个项目。</p>
   </div>
   ```

配置里的 `--color-*: initial` 会清空 Tailwind 默认色板，强制只用语义色。觉得太严格可以删掉那一行。

## 三条原则

1. **只用语义 token。** 写 `text-fg-muted`，不写 `text-zinc-600` 或色值。
2. **少即是多。** 1 个品牌色、3 级文字色、9 个字号样式、8 档间距、4 档圆角。
3. **两个主题同时设计。** 每加一个颜色，Light 和 Dark 的值同时定，并各验一次对比度。

所有文字色在两个主题、三层背景上都达到 WCAG AA（≥ 4.5:1）。

## 修改规范

新增颜色或字号时，先改 `tokens.json`、`tailwind/starter-ui.css` 和 `index.html` 三处，再在代码里使用。宁可多一个 token，也不要在组件里写孤立的色值。

## License

[MIT](LICENSE)，可以自由复制、修改和用于商业项目。
