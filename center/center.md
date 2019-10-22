#### 怎么让一个 div 水平垂直居中 ?

1. 重要
```css
div.parent {
    display: flex;
    justify-content: center;
    align-items: center;
}
```
2. 重要-常用
```css
div.parent {
    position: relative; 
}
div.child {
    position: absolute; 
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
/* 或者 */
div.child {
    width: 50px;
    height: 10px;
    position: absolute;
    top: 50%;
    left: 50%;
    margin-left: -25px;
    margin-top: -5px;
}
/* 或者 */
div.child {
    width: 50px;
    height: 10px;
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    margin: auto;
}
```
3. 加分-网格布局
```css
div.parent {
    display: grid;
}
div.child {
    justify-self: center;
    align-self: center;
}
```
4. 需要知道
```css
div.parent{
  display:flex;
}
div.child{
  margin:auto;
}
```

