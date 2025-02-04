---
title: <blend-mode>
slug: Web/CSS/blend-mode
---
{{CSSRef}}

**`<blend-mode>`** 是一种 [CSS](/zh-CN/docs/Web/CSS) [数据类型](/zh-CN/docs/Web/CSS/CSS_Types)，用于描述当元素重叠时，颜色应当如何呈现。它被用于 {{cssxref("background-blend-mode")}} 和 {{cssxref("mix-blend-mode")}} 属性。

当层重叠时，混合模式是计算像素最终颜色值的方法，每种混合模式采用前景和背景的颜色值，执行其计算并返回最终的颜色值。最终的可见层是对混合层中的每个重叠像素执行混合模式计算的结果。

## 语法

`<blend-mode>` 数据类型被定义为下列关键词中的任意一个。

### 属性值

- `normal`
  - : 最终颜色永远是顶层颜色，无论底层颜色是什么。其效果类似于两张不透明的纸重叠（overlapping）在一起。
- `multiply`
  - : 最终颜色为顶层颜色与底层颜色相乘的结果。如果叠加黑色层，则最终层必为黑色层，叠加白色层不会造成变化。其效果类似于在透明薄膜上重叠印刷的两个图像。
- `screen`
  - : 最终的颜色是**反转顶层颜色和底层颜色，将反转后的两个颜色相乘，再反转相加得到的和**得到的结果。
    黑色层不会造成变化，白色层导致白色最终层。
    其效果类似于（被投影仪）投射到投影屏幕上的两个图像。
- `overlay`
  - : 如果底层颜色比顶层颜色深，则最终颜色是 `multiply` 的结果，如果底层颜色比顶层颜色浅，则最终颜色是 `screen` 的结果。
    此混合模式相当于顶层与底层互换后的 `hard-light`。
- `darken`
  - : 最终颜色是由每个颜色通道下，顶底两层颜色中的最暗值所组成的颜色。
- `lighten`
  - : 最终颜色是每个颜色通道下，顶底两层颜色中的最亮值所组成的颜色。
- `color-dodge`
  - : 最终颜色是将底部颜色除以顶部颜色的反色的结果。黑色前景不会造成变化。前景如果是背景的反色，会得到白色（fully lit color，完全亮起的颜色，应当为白色）。
    此混合模式类似于 `screen`，但是，前景只需要和背景的反色一样亮，最终图像就会变为全白。
- `color-burn`
  - : 最终颜色是**反转底部颜色，将反转后的值除以顶部颜色，再反转除以后的值**得到的结果。
    白色的前景不会导致变化，前景如果是背景的反色，会得到黑色。
    此混合模式类似于 `multiply`，但是，前景只需要和背景的反色一样暗，最终图像就会变为全黑。
- `hard-light`
  - : 如果顶层颜色比底层颜色深，则最终颜色是 `multiply` 的结果，如果顶层颜色比底层颜色浅，则最终颜色是 `screen` 的结果。
    此混合模式相当于顶层与底层互换后的 `overlay`。其效果类似于在背景层上（用前景层）打出一片*刺眼*的聚光灯。
- `soft-light`
  - : 最终颜色类似于 `hard-light` 的结果，但更加柔和一些。此混合模式的表现类似 `hard-light`。其效果类似于在背景层上（用前景层）打出一片*发散*的聚光灯。
- `difference`
  - : 最终颜色是 两种颜色中较浅的颜色 减去 两种颜色中较深的颜色 得到的结果。
    黑色层不会造成变化，而白色层会反转另一层的颜色。

- `exclusion`
  - : 最终颜色类似于 `difference`，但对比度更低一些。和 `difference` 相同，黑色层不会造成变化，而而白色层会反转另一层的颜色。
- `hue`
  - : 最终颜色由顶部颜色的*色调*和底部颜色的*饱和度*与*亮度*组成。
- `saturation`
  - : 最终颜色由顶部颜色的*色调*和底部颜色的*饱和度*与*发光度*组成。饱和度为零的纯灰色背景层不会造成变化。
- `color`
  - : 最终颜色由顶部颜色的*色调*与*饱和度*和底部颜色的*亮度*组成。
    此效果保留了灰度级别，可用于为前景着色。（The effect preserves gray levels and can be used to colorize the foreground.）
- `luminosity`
  - : 最终颜色由顶部颜色的亮度和底部颜色的色调和饱和度组成。此混合模式相当于顶层与底层互换后的 `color`。

## 混合模式的插值

混合模式之间的更改暂无插值。任何变化都会立即发生。

## 规范

{{Specifications}}

## 浏览器兼容性

{{Compat("css.types.blend-mode")}}

## 另请参阅

- 使用此类型的属性值：{{cssxref("background-blend-mode")}} 和 {{cssxref("mix-blend-mode")}}

其他网站上对各种混合模式的说明与介绍：

- Wikipedia 上的[混合模式](http://en.wikipedia.org/wiki/Blend_modes)（暂无中文）
- Adobe 提供的 [Blending modes in Adobe Photoshop](https://helpx.adobe.com/photoshop/using/blending-modes.html)（英文）
