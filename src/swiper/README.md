---
title: Swiper 轮播图
description: 用于循环轮播一组图片或内容，也可以滑动进行切换，轮播动效时间可以设置。
spline: message
isComponent: true
---

<span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20lines-95%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20functions-94%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20statements-95%25-blue" /></span><span class="coverages-badge" style="margin-right: 10px"><img src="https://img.shields.io/badge/coverages%3A%20branches-90%25-blue" /></span>
## 引入

全局引入，在 miniprogram 根目录下的`app.json`中配置，局部引入，在需要引入的页面或组件的`index.json`中配置。

```json
"usingComponents": {
  "t-swiper": "tdesign-miniprogram/swiper/swiper",
  "t-swiper-nav": "tdesign-miniprogram/swiper/swiper-nav",
}
```

### 组件说明

从 `0.32.0` 版本开始，依赖原生 `swiper` 组件实现，移除了 `swiper-item` 组件，新增了 `list` 属性；

## 代码演示

多种轮播样式，通过 `navigation` 设置导航样式，没有值则不显示，也可以自定义 `nav` 组件

<img src="https://tdesign.gtimg.com/miniprogram/readme/swiper.gif" width="375px" height="50%">

### 组件类型

#### 点状（dots）轮播图

{{ base }}

#### 点条状（dots-bar）轮播图

{{ custom }}

#### 分式（fraction）导航器轮播图

{{ fraction }}

#### 切换按钮（controls）轮播图

{{ nav-btn }}

#### 卡片式（cards）轮播图

{{ cards }}

### 组件样式

#### 垂直模式

{{ vertical }}

## API
### Swiper Props

名称 | 类型 | 默认值 | 说明 | 必传
-- | -- | -- | -- | --
autoplay | Boolean | true | 是否自动播放 | N
current | Number | 0 | 当前轮播在哪一项（下标） | N
default-current | Number | undefined | 当前轮播在哪一项（下标）。非受控属性 | N
custom-style | String | - | `0.25.0`。自定义组件样式 | N
direction | String | horizontal | 轮播滑动方向，包括横向滑动和纵向滑动两个方向。可选项：horizontal/vertical | N
display-multiple-items | Number | 1 | `0.32.0`。同时显示的滑块数量 | N
duration | Number | 300 | 滑动动画时长 | N
easing-function | String | default | `0.32.0`。指定 swiper 切换缓动动画类型。可选项：default/linear/easeInCubic/easeOutCubic/easeInOutCubic | N
height | String / Number | '192px' | 轮播的高度；默认单位 `px` | N
interval | Number | 5000 | 轮播间隔时间 | N
list | Array | - | `0.32.0`。图片列表。TS 类型：`string[]` | N
loop | Boolean | true | 是否循环播放 | N
navigation | Object / Slot | - | 导航器全部配置 | N
next-margin | String / Number | 0 | `0.32.0`。后边距，可用于露出后一项的一小部分。默认单位 `px` | N
pagination-position | String | bottom | 页码信息展示位置。可选项：top-left/top/top-right/bottom-left/bottom/bottom-right | N
previous-margin | String / Number | 0 | `0.32.0`。前边距，可用于露出前一项的一小部分。默认单位 `px` | N
snap-to-edge | Boolean | false | `0.32.0`。当 swiper-item 的个数大于等于 2，关闭 circular 并且开启 previous-margin 或 next-margin 的时候，可以指定这个边距是否应用到第一个、最后一个元素 | N

### Swiper Events

名称 | 参数 | 描述
-- | -- | --
change | `(current: number, source: SwiperChangeSource)` | 轮播切换时触发。[详细类型定义](https://github.com/Tencent/tdesign-miniprogram/tree/develop/src/swiper/type.ts)。<br/>`type SwiperChangeSource = 'autoplay' \| 'touch' \| 'nav'`<br/>

### SwiperNavigation

名称 | 类型 | 默认值 | 说明 | 必传
-- | -- | -- | -- | --
custom-style | String | - | `0.25.0`。自定义组件样式 | N
min-show-num | Number | - | 小于这个数字不会显示导航器 | N
show-controls | Boolean | false | 是否显示两侧的控制按钮 | N
type | String | - | 导航器类型，点状(dots)、点条状(dots-bar)、分式(fraction)等。TS 类型：`SwiperNavigationType` `type SwiperNavigationType = 'dots' \| 'dots-bar' \| 'fraction'`。[详细类型定义](https://github.com/Tencent/tdesign-miniprogram/tree/develop/src/swiper/type.ts) | N
