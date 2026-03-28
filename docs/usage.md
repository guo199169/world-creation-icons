# 使用指南

## 图标格式说明

### SVG 格式
- 优点：无限缩放不失真、文件小、可编辑
- 适用场景：Web 项目、高分辨率屏幕、需要动态改色

### PNG 格式
- 优点：兼容性好、无需额外处理
- 适用场景：快速原型、不支持 SVG 的旧系统

## 集成方式

### Web 项目

```html
<!-- 直接引用 SVG -->
<svg class="icon">
  <use href="/icons/world.svg#world"></use>
</svg>

<!-- 或使用 PNG -->
<img src="/icons/world-24.png" alt="世界">
```

### React/Vue 组件

```jsx
// SVG 组件示例
const WorldIcon = () => (
  <svg width="24" height="24">
    <use href="/svg/world.svg#world"></use>
  </svg>
);
```

### CSS 图标字体（可选）

如需生成图标字体，可使用 `icon-font` 工具：

```bash
npm install -g icon-font
icon-font --src=svg/*.svg --dest=fonts/
```

## 最佳实践

1. **保持统一尺寸**：建议使用 24x24 作为标准尺寸
2. **命名规范**：使用小写字母和连字符，如 `world-creation.svg`
3. **颜色管理**：SVG 使用 `currentColor` 以便 CSS 控制
4. **性能优化**：SVG 文件使用 `svgo` 压缩

## 自定义颜色

```css
.icon {
  color: #007bff; /* SVG 图标会自动继承 color 属性 */
}
```

## 动画效果

```css
.icon {
  transition: transform 0.3s ease;
}

.icon:hover {
  transform: scale(1.1);
}
```
