#### css-record

记录 css 一些使用技巧

- 本项目 HTML 文件都是移动端显示
- HTML 文件用来测试
- md 文件用来总结

- https://juejin.im/post/5dafc3df5188257a63539c64?utm_source=gold_browser_extension
- https://lucifer.ren/fe-interview/#/?id=%e7%ae%80%e5%8e%86-amp-%e4%b8%aa%e4%ba%ba%e4%b8%bb%e9%a1%b5-%f0%9f%93%96

```css
div {
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;
  overflow: hidden;
}
```

#### vertical-align

[https://www.zhangxinxu.com/wordpress/2015/08/css-deep-understand-vertical-align-and-line-height/](https://www.zhangxinxu.com/wordpress/2015/08/css-deep-understand-vertical-align-and-line-height/)

#### 文字垂直居中的方法

- iOS 和部分 Android 在使用 `button` 标签时，如果设置等高的 `line-height` ，会出现文字下偏移的情况
- iOS 使用默认字体（不设置字体）时，奇数字号会出现上偏移 1px 的情况
- Android 在 `字号 % 4 !== 0` 时（如 11px，14px），会出现文字较大幅度上偏移的情况
- `字号 % 4 === 0` 时 iOS 和 Android 表现正常，不需要特殊处理
- 部分 Android 在 smzdm webview 内不支持 12px 以下的字号（会强制渲染为 12px）

##### 解决方案

设置字体 `font-family: "PingFang SC", "Heiti SC", "San Francisco", "Helvetica";`
iOS
在 iOS 下，推荐使用 `button` 标签

注意：不要给 `button` 标签设置 `与标签等高的line-height`

Android

```html
<!-- data-text属性值要和标签文案相同 -->
<button data-text="标签文案">标签文案</button>
<button class="Android" data-text="标签文案">标签文案</button>

<style>
  button {
    position: relative;
    font-family: "PingFang SC", "Heiti SC", "San Francisco", "Helvetica";
    height: 30px;
    line-height: 1;
    outline: none;
    border: none;
    background: #e62828;
    font-size: 13px;
    color: #fff;
    overflow: hidden;
  }

  button.Android::after {
    content: attr(data-text);
    position: absolute;
    top: 0;
    left: 0;
    width: 400%;
    height: 400%;
    line-height: 120px;
    font-size: 4em;
    color: inherit;
    background: inherit;
    transform: scale(0.25);
    transform-origin: 0 0;
  }
</style>
```

#### 怎么让页面变灰实现代码

```html
<style>
  html {
    filter: grayscale(100%);
    -webkit-filter: grayscale(100%);
    -moz-filter: grayscale(100%);
    -ms-filter: grayscale(100%);
    -o-filter: grayscale(100%);
    filter: progid:DXImageTransform.Microsoft.BasicImage(grayscale=1);
    -webkit-filter: grayscale(1);
  }
</style>
```

## Tools 层代码实现

SassMagic 引入 [https://github.com/W3cplus/SassMagic](https://github.com/W3cplus/SassMagic)


## vue.config.js 配置全局引入文件

[https://cli.vuejs.org/guide/css.html#passing-options-to-pre-processor-loadersgit ](https://cli.vuejs.org/guide/css.html#passing-options-to-pre-processor-loaders)
```js
module.exports = {
  css: {
    loaderOptions: {
      scss: {
        prependData: `@import "~@/variables.sass"`
      },
      css: {
        // 这里的选项会传递给 css-loader
      },
      postcss: {
        // 这里的选项会传递给 postcss-loader
      }
    }
  }
}
```

## scroll-snap-align

## text-transform

text-transform CSS属性指定如何将元素的文本大写。它可以用于使文本显示为全大写或全小写，也可单独对每一个单词进行操作

https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-transform

text-transform: capitalize; 首字母大写
 
## hsl

```css
.green {
  background-color: hsl(120, 100%, 50%);
}
```

## linear-gradient

```css
div {
  border-radius: 20px;
  width: 70%;
  height: 400px;
  margin: 50px auto;
  background: linear-gradient(35deg, #CCFFFF, #FFCCCC);

}
```

## repeating-linear-gradient

创建一个由重复线性渐变组成的<image>

```css
  div{
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin:  50 auto;
    background: repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    );
  }

/* 斑马线 */
#grad2 {
  background-image: repeating-linear-gradient(-45deg,
      transparent,
      transparent 25px,
      rgba(255,255,255,1) 25px,
      rgba(255,255,255,1) 50px);
}
```

## transform

把 id 为 ball2 的元素放大到原始大小的 1.5 倍。

```css
#ball2 {
    transform: scale(1.5);
  }
```

### skewX

skewX 函数使指定元素沿 X 轴翻转指定的角度，想必你已经猜到了，skewY 属性使指定元素沿 Y 轴（垂直方向）翻转指定角度。

```css
#ball2 {
  transform: skewY(24deg);
}
```

## 使用 CSS 创建一个图形

```html
<style>
  .center {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100px;
    height: 100px;
    background-color: transparent;
    border-radius: 50%;
    box-shadow: 25px 10px 0 0 blue;
  }
</style>
<div class="center"></div>
```

## 一个粉色的心

```html
<style>
  .heart {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: pink;
    height: 50px;
    width: 50px;
    transform: rotate(-45deg);
  }
  .heart::after {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 0px;
    left: 25px;
  }
  .heart::before {
    content: '';
    background-color: pink;
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: -25px;
    left: 0px;
  }
</style>
<div class="heart"></div>
```

## 了解 CSS 的关键帧和动画是如何工作的

```html
<style>
  div {
    height: 40px;
    width: 70%;
    background: black;
    margin: 50px auto;
    border-radius: 5px;
  }
  @keyframes rainbow {
  0% {
    background-color: blue;
  }
  50% {
    background-color: green;
  }
  100% {
    background-color: yellow;
  }
}
  #rect {
    animation-name: rainbow;
  animation-duration: 4s;

  }
</style>
<div id="rect"></div>
```
## 使用CSS动画更改按钮的悬停状态

```html
<style>
  button {
    border-radius: 5px;
    color: white;
    background-color: #0F5897;
    padding: 5px 10px 8px 10px;
  }
  @keyframes background-color {
    100% {
      background-color: #4791d0;
    }
  }
  button:hover {
    animation-name: background-color;
    animation-duration: 500ms;
  }
</style>
<button>Register</button>
```

## 修改动画的填充模式

```html
<style>
  button {
    border-radius: 5px;
    color: white;
    background-color: #0F5897;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    animation-name: background-color;
    animation-duration: 500ms;
    /* 只修改这一行下面的代码 */
    animation-fill-mode: forwards;
    /* 只修改这一行上面的代码 */
  }
  @keyframes background-color {
    100% {
      background-color: #4791d0;
    }
  }
</style>
<button>Register</button>
```
## 使用 CSS 动画创建动画

```html
<style>
  div {
    height: 40px;
    width: 70%;
    background: black;
    margin: 50px auto;
    border-radius: 5px;
    position: relative;
  }

  #rect {
    animation-name: rainbow;
    animation-duration: 4s;
  }

  @keyframes rainbow {
    0% {
      background-color: blue;
      top: 0px;
      left: 0px;
    }
    50% {
      background-color: green;
      top: 50px;
      left: 25px;
    }
    100% {
      background-color: yellow;
      top: 0px;
      left: -25px;
    }
  }
</style>
<div id="rect"></div>
```

## 通过从左到右淡化元素来创建视觉方向

```html
<style>

  #ball {
    width: 70px;
    height: 70px;
    margin: 50px auto;
    position: fixed;
    left: 20%;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: fade;
    animation-duration: 3s;
  }

  @keyframes fade {
    50% {
      left: 60%;
      opacity: 0.1;
    }
  }

</style>

<div id="ball"></div>
```
## 使用无限的动画计数制作永不停止的动画

```html
<style>

  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```

## 使用无限的动画计数制作 CSS 心跳

```html
<style>
  .back {
    position: fixed;
    padding: 0;
    margin: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: white;
    animation-name: backdiv;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }

  .heart {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: pink;
    height: 50px;
    width: 50px;
    transform: rotate(-45deg);
    animation-name: beat;
    animation-duration: 1s;
    animation-iteration-count: infinite;
  }
  .heart:after {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: 0px;
    left: 25px;
  }
  .heart:before {
    background-color: pink;
    content: "";
    border-radius: 50%;
    position: absolute;
    width: 50px;
    height: 50px;
    top: -25px;
    left: 0px;
  }

  @keyframes backdiv {
    50% {
      background: #ffe6f2;
    }
  }

  @keyframes beat {
    0% {
      transform: scale(1) rotate(-45deg);
    }
    50% {
      transform: scale(0.6) rotate(-45deg);
    }
  }

</style>
<div class="back"></div>
<div class="heart"></div>
```

## 以可变速率来给元素添加动画

```html
<style>
  .stars {
    background-color: white;
    height: 30px;
    width: 30px;
    border-radius: 50%;
    animation-iteration-count: infinite;
  }

  .star-1 {
    margin-top: 15%;
    margin-left: 60%;
    animation-name: twinkle-1;
    animation-duration: 1s;
  }

  .star-2 {
    margin-top: 25%;
    margin-left: 25%;
    animation-name: twinkle-2;
    animation-duration: 1s;
  }

  @keyframes twinkle-1 {
    50% {
      transform: scale(0.5);
      opacity: 0.5;
    }
  }

  @keyframes twinkle-2 {
    20% {
      transform: scale(0.5);
      opacity: 0.5;
    }
  }

  #back {
    position: fixed;
    padding: 0;
    margin: 0;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(black, #000099, #66c2ff, #ffcccc, #ffeee6);
  }
</style>

<div id="back"></div>
<div class="star-1 stars"></div>
<div class="star-2 stars"></div>
```

