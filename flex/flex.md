css-flex 需要掌握知识点

#### 内容宽度等分

```css
.box {
    display: flex;
    width: 300px;
    height: 100px;
}
.box div{
    width: 100%;
    border: 1px solid #000;
}
```
```html
<div class="box">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>
```

#### 垂直居中问题

见 center.md

#### 简单说一下flex弹性布局

```
flex-direction: row(主轴为水平方向)/column(主轴为竖直方向)/row-reverse(从右到左水平方向)/column-reverse(从下至上竖直方向)

flex-wrap: nowrap(自动缩小项目，不换行)/wrap(换行，且第一行在上方)/wrap-reverse(换行，第一行在下面)

justify-content: flex-start(左对齐)/flex-end(右对齐)/center(居中对齐)/space- between(两端对齐)/space-around(沿轴线均匀分布)

align-items: flex-start(顶端对齐)/flex-end(底部对齐)/center(竖直方向上居中对齐)/baseline(基线对齐)/stretch(当item未设置高度时，item将和容器等高对齐)

```
