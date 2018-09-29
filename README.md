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