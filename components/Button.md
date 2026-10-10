# Button

触发操作的按钮，分 primary、secondary、ghost、danger 四种，sm / md / lg 三个尺寸。

## 什么时候用哪种
- **primary**：页面或弹窗里最重要的那一个操作。一屏只放一个。
- **secondary**：与 primary 并列的次要操作，如"取消"。
- **ghost**：工具栏、列表行内等低强调操作。
- **danger**：删除、移除等不可逆操作。放在确认弹窗里，不要和 primary 并排出现。

## 尺寸
- `sm` 32px：表格行内、紧凑工具栏。
- `md` 36px：Web 端默认。
- `lg` 44px：移动端默认（满足 44px 最小触控区域）。

## Tailwind 写法

```html
<!-- 共用基础 -->
<button class="inline-flex items-center justify-center gap-2 h-9 px-4 rounded-md
  text-label font-medium transition-colors
  focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-primary
  disabled:opacity-50 disabled:cursor-not-allowed
  bg-primary text-primary-fg hover:bg-primary-hover">发送邀请</button>
```

把最后一行换成对应变体：

| 变体 | 颜色类 |
|---|---|
| primary | `bg-primary text-primary-fg hover:bg-primary-hover` |
| secondary | `bg-surface text-fg border border-border-strong hover:bg-border` |
| ghost | `bg-transparent text-fg hover:bg-surface` |
| danger | `bg-danger text-danger-fg hover:bg-danger-hover` |

尺寸：`sm` 用 `h-8 px-3`，`lg` 用 `h-11 px-6`。

## 注意
- 文案用动词开头（"保存更改"），不要只写"确定"。
- 图标按钮必须加 `aria-label`。
- 禁用态只降低透明度，不换颜色，两个主题自动一致。
