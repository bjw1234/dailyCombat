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

**声明一个局部变量：**

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