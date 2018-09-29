# 路径
file:///C:/Users/家伟/Desktop/桌面文件/a随手测试练习项目在这里呀/dailyCombat

# 按钮文字滑动特效

* attr()获取元素属性

```html
<span data-text="hello">hello</span>

// 在css中可以这样得到它的属性值

span::before {    
    content: attr(data-text);    
}
```

* 奇数和偶数

```css
/* 偶数 = 2n */
span:nth-child(even) {
}

/* 奇数 = 2n+1 */
span:nth-child(odd) {
}
```

# 矩形旋转loader特效

* 行内元素和块状元素之间的转换

1. 使用display属性
2. `float`会使行内元素变成块状元素
3. `position:absolute/fixed`同2

* 关键帧动画

```css
animation: name duration timing-function delay iteration-count direction fill-mode play-state;
animation: 动画名称 执行时间 速度曲线 延时时间 执行次数 动画播放顺序 结束时应用的样式 播放的状态（paused|running）
```