# Badge

标记状态或分类的小标签，用一个彩色圆点表达状态，文字保持中性色。

## 为什么用圆点而不是彩色底
浅色模式下，12px 的彩色文字放在同色浅底上对比度只有约 4:1，达不到 4.5:1。改成"中性文字 + 彩色圆点"后，文字始终清晰，颜色只做辅助提示，色盲用户也能靠文字理解。

## Tailwind 写法

```html
<!-- 状态 -->
<span class="inline-flex items-center gap-1 h-[22px] px-2 rounded-sm
  border border-border text-caption font-medium text-fg-muted">
  <span class="size-1.5 rounded-full bg-success"></span>运行中
</span>

<!-- 品牌（新功能、Beta 等） -->
<span class="inline-flex items-center h-[22px] px-2 rounded-sm
  bg-primary-subtle text-primary text-caption font-medium">新功能</span>
```

圆点颜色：`bg-success` / `bg-warning` / `bg-danger`，中性状态去掉圆点。

## 注意
- 文字 2–4 个字，不放句子。
- Badge 不可点击；需要点击就用 ghost 按钮。
