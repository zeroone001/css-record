1. 清除浮动的方式有哪些？
```css
.clearfix::after {
    clear: both;
    content: ' ';
}
.clearfix::before, .clearfix::after {
    display: table;
    content: ' ';
}
```
