# 路径
file:///C:/Users/家伟/Desktop/桌面文件/a随手测试练习项目在这里呀/dailyCombat

# 按钮文字滑动特效

* 一. attr()获取元素属性

```html
<span data-text="hello">hello</span>

<!-- 在css中可以这样得到它的属性值 -->
<style>
span::before {    
    content: attr(data-text);    
}
</style>
```

* 二. 奇数和偶数

```css
/* 偶数 = 2n */
span:nth-child(even) {
}

/* 奇数 = 2n+1 */
span:nth-child(odd) {
}
```

# 矩形旋转loader特效

* 一. 行内元素和块状元素之间的转换

1. 使用display属性
2. `float`会使行内元素变成块状元素
3. `position:absolute/fixed`同2

* 二. 关键帧动画

```css
/* 名时曲 延次顺 */
animation: name duration timing-function delay iteration-count direction fill-mode play-state;
animation: 动画名称 执行时间 速度曲线 延时时间 执行次数 动画播放顺序 结束时应用的样式 播放的状态（paused|running）
```

# 立体toggle交互控件

* 一. box-shadow效果

```css
/* 
水平偏移 | 垂直偏移 | 模糊半径 | 扩展半径 | 颜色
offset-x | offset-y | blur-radius | spread-radius | color */
box-shadow: 1px 1px 8px 5px black;

/*
内阴影效果
inset | offset-x | offset-y | color */
```

* 二. gradient渐变

```css
/*  方向
    to left, to top, to bottom right, ...
    颜色节点
    red 20%, blue 50%, yellow 100%
*/
background: linear-gradient(direction, color-stop1, color-stop2, ...);
```

# 金属光泽3D按钮特效

* 一. CSS变量

**声明一个局部变量：**

```css
element {
    --main-color: brown;
}

/* 使用 */
element {
    background: var(--main-color);
}
```

**声明一个全局变量：**

```css
:root {
    --global-color: #666;
}

/* 使用 */
.demo {
    background: var(--global-color);
}
```

**解决的问题：**
1. 为了网站的可维护性。
2. 名称信息包含了语义信息。

**注意：**

CSS变量可以被继承。

* 二. 3D样式

```css
element {
    /* 浏览器窗口距离3D物体的距离为800px */
    perspective: 800px;
    transform: perspective(500px) rotateY(-15deg);

    /* 视点  50% 50%在浏览器的中心 */
    perspective-origin: 50% 50%;
}
```

# 创作一种侧立图书的特效

* 一. `transfrom-origin`

更改一个元素变形的原点。

```css
/* x-offset-keyword | y-offset */
transform-origin: left 2px;

/* x-offset-keyword | y-offset-keyword */
transform-origin: right top;

/* 如果有三个值，那第三个值表示z轴方向的偏移量 */
/* x-offset-keyword | y-offset-keyword | z-offset */
transform-origin: right bottom 10px;
```

* 二. `filter`滤镜的使用

```css
filter: brightness(0.6);

/* 给图像设置高斯模糊 */ 
blur(px)     

/* 设置图像的明暗。 0%（全黑）--100%（无变化）--max(更亮） */ 
brightness(%)    

/* 调整图像的对比度。 0%（全黑）--100%（无变化）--max */ 
contrast(%)    

/* 将图像转化为灰度图像。 0%（无变化）--100%（完全的灰度图像） */ 
grayscale(%)    
```

# 充电loader效果

* 一. `currentColor` CSS3关键字

这个关键字的值 = color的值

```css
element {
    color: red;
    border: 1px solid currentColor;
}
```

* 二. `background-position` 属性

`background-position` 属性设置背景图像的起始位置。
定义背景图像`background-image`的位置，背景图形如要要重复，将从这一点开始。

```css
element {
    /* 默认值 第一个值为水平位置，第二个值为垂直位置 */
    background-position: 0% 0%;
    /* 定义背景图在右上角，如果top缺失，
    则默认值为center，也就是说垂直方向会居中 */
    background-position: right top;

    /* 一个更为牛逼的用法
    背景图距离left为15px，距离top为30px */
    background-position: left 15px top 30px;
}
```

* 三. `background-image` 属性

设置元素背景图像。元素的背景占据了元素的全部尺寸，包括content、padding、border，但是不包括外边距。

如果设置`no-repeat`属性，则背景图片默认是从padding部分开始的。

背景属性是支持多个图片：

```css
element {
    background-image: url(img_flwr.gif), url(paper.gif);
    background-position: right bottom, left top;
    background-repeat: no-repeat, repeat;
    padding: 15px;
}
```

背景图片支持渐变：

```css
element {
    background-image: linear-gradient(to right, white, white);    
}
```

* 四. `background-origin` 属性

属性规定 `background-position` 属性相对于什么位置来定位。

`border-box`:	背景图像相对于内边距框来定位。	
`padding-box`:	背景图像相对于边框盒来定位。	
`content-box`:	背景图像相对于内容框来定位。

* 五. `background-size` 属性

`length` 设置背景图片的高度和宽度。
`percentage` 以父元素的百分比来设置背景图片的宽度和高度。

第一个值设置宽度，第二个值设置高度。
如果只设置一个值，则第二个值会被设置为“auto”。

```css
element {
    background-size: 50px 40px;
    /* 宽度为父元素的百分之70，高度auto */
    background-size: 70% /*auto*/;
}
```

`cover` 把背景图像扩展至最大，以使背景图像完全覆盖背景区域。（背景图像超出内容区域）

`contain` 把图像扩展至最大尺寸，以使宽度和高度完全适应内容区域。（背景图像未能填满内容区域）

* 六. `background-clip` 属性

该属性规定背景的绘制区域。

语法

```css
background-clip: border-box|padding-box|content-box;
```

`border-box`背景被裁剪到边框盒。	
`padding-box`背景被裁剪到内边距框。	
`content-box`背景被裁剪到内容框。

# CSS画panda熊猫  

* 一. `border-radius`属性

```css
element {
    /* 以下两种写法相同 */
    border-radius: 10px;

    /* 水平半径/垂直半径（左上、右上、左下、右下） */
    border-radius: 10px 10px 10px 10px / 10px 10px 10px 10px;
}
```

* 二. `animation` 属性

```css
direction
element {
   /* 名称、时间、曲线、延时、次数、顺序 */ 
   animation: animate 1s ease-in-out -1s infinite alternate;
}
```
注意这里的动画执行顺序：
`animation-direction: alternate` 表示交替、轮流执行动画

* 三. CSS的径向渐变

1.指定渐变形状，并指定渐变起始点位置

```css
element {
    background-image: radial-gradient(circle at 30% 50%, yellow, red);
}
```

2.指定渐变的终止点位置

`closest-side`: 渐变中心距离容器最近的边。

`closest-corner`: 渐变中心距离容器最近的角。

`farthest-side`: 渐变中心距离容器最远的边。

`farthest-corner`: 渐变中心距离容器最远的角。

```css
element {
    background: radial-gradient(closest circle at 50px 50px, yellow, red);
}
```

3.指定颜色断点

```css
element {
    /* 在(4.5em, 2em)这个点处有一个1em宽度，颜色为white的circle */
    background: radial-gradient(circle at 4.5em 2em, white 1em, transparent 1em);
}
```

4.椭圆类型的径向渐变

```css
element {
    background: radial-gradient(50px 100px ellipse, transparent 40px, yellow 41px, red);
}
```

`50px 100px ellipse`中的第一个数值`50px`表示横轴半径，`100px`表示纵轴半径。
透明的颜色节点为40px,黄色的颜色节点为41px，剩余内容为红色。

`border-image`无法和`border-radius`同时生效。
但是，可以通过嵌套标签可以完成同样的效果。
