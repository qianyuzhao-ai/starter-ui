# Input

单行文本输入，始终搭配标签和可选的帮助文字，支持默认、聚焦、错误、禁用状态。

## 结构
标签（`label`）→ 输入框 → 帮助文字或错误提示（`caption`）。三者间距 4px，表单项之间 24px。

## Tailwind 写法

```html
<label class="flex flex-col gap-1">
  <span class="text-label font-medium text-fg">项目名称</span>
  <input class="h-9 w-full px-3 rounded-md bg-bg text-body text-fg
    border border-border-strong placeholder:text-fg-subtle
    focus:outline-none focus:border-primary focus:ring-1 focus:ring-primary
    disabled:opacity-50 disabled:bg-surface
    aria-[invalid=true]:border-danger"
    placeholder="例如：landing-test">
  <span class="text-caption text-fg-subtle">只能包含小写字母和连字符</span>
</label>
```

错误时：输入框加 `aria-invalid="true"`，帮助文字换成 `text-danger` 的错误提示。

## 注意
- 边框用 `border-strong` 而不是 `border`：输入框边界要能被看清（≥3:1）。
- 不要只用占位符代替标签，输入后标签就消失了。
- 移动端把输入框改为 `h-11 text-body-lg`（16px），否则 iOS Safari 聚焦时会放大页面。
- 错误提示写清楚怎么改，而不只是"格式错误"。
