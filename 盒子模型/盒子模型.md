# 盒子模型

- box-shadow
```css
/* inset | offset-x | offset-y | spread-radius | color */
box-shadow: inset 0 0 1em gold;

/* offset-x | offset-y | blur-radius | spread-radius | color */
box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
```

- 强制不换行
```css
div{
white-space:nowrap;
}
```

- 如何保持固定比例
padding-top 的百分比是相对于宽度的，所以可以用来做比例布局

### 保持盒子固定比例缩放，内部图片垂直水平居中

核心是： item_logo height 为 0 ,padding-bottom 为相对图片的比例；div.logo 通过 height: 100% 获取到高度，对img 进行布局。
```html
<div class="item_logo">
  <div class="logo">
    <img src="{$value.logo_url}">
  </div>
</div>
```

```css
.waltz_list .item_logo {
	position: relative;
	box-sizing: border-box;
	padding-bottom: 65%;
	width: 100%;
	height: 0;
	overflow: hidden;
	background-color: #ffffff;
	-webkit-transition: all 0.2s ease-in;
	transition: all 0.2s ease-in;
}
.waltz_list .item_logo .logo {
	position: absolute;
	left: 0;
	top: 0;
	display: flex;
	justify-content: center;
	align-items: center;
	width: 100%;
	height: 100%;
}
.waltz_list .item_logo img {
	max-width: 100%;
}
```

### 图片大小显示
max-width 支持百分比
max-height 
