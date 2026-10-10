# Card

把一组相关内容装在一起的容器，有默认（平铺在页面上）和浮层（弹窗、下拉）两种层级。

## 层级
- **默认**：`surface` 底色 + `border` 描边，用于页面里的内容分组。
- **浮层**：`surface-raised` 底色 + `shadow-lg`，用于弹窗、Popover。浅色下靠阴影浮起，深色下靠底色变亮浮起。

## Tailwind 写法

```html
<div class="bg-surface border border-border rounded-lg p-4">
  <h3 class="text-h3 font-semibold text-fg">邀请新成员</h3>
  <p class="text-body text-fg-muted mt-1">成员可以查看和编辑这个项目。</p>
  <div class="flex justify-end gap-2 mt-4">
    <!-- secondary + primary 按钮 -->
  </div>
</div>
```

浮层：把第一行换成 `bg-surface-raised border border-border rounded-lg p-4 shadow-lg`。`shadow-lg` 已在总配置里按主题定义好，深色下会自动加深。

## 注意
- 内边距默认 16px，内容多的卡片可用 24px，不要更多。
- 卡片不要嵌套卡片；需要再分组时用分割线（`border-t border-border`）。
- 操作按钮靠右，主操作在最右边。
