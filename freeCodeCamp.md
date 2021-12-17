# freeCodeCamp


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

## 使用关键字更改动画定时器 animation-timing-function

animation-timing-function 用来定义动画的速度曲线。 速度曲线决定了动画从一套 CSS 样式变为另一套所用的时间。 如果要描述的动画是一辆车在指定时间内（animation-duration）从 A 运动到 B，那么 animation-timing-function 表述的就是车在运动中的加速和减速等过程

有一些预定义的关键字可用于常见的选项。 比如，默认值是 ease，动画以低速开始，然后加快，在结束前变慢。 其它常用的值包括 ease-out：动画以高速开始，以低速结束；ease-in，动画以低速开始，以高速结束；linear：动画从头到尾的速度是相同的

```html
<style>

  .balls {
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 {
    left:27%;
    animation-timing-function: linear;
  }
  #ball2 {
    left:56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```

## 学习贝塞尔曲线的原理

```html
<style>

  .balls{
    border-radius: 50%;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #ball1 {
    left: 27%;
    animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
  }
  #ball2 {
    left: 56%;
    animation-timing-function: ease-out;
  }

  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }

</style>

<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```

## 使用贝塞尔曲线移动图形

```html
<style>
  .balls{
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 27%;
    animation-timing-function: cubic-bezier(0, 0, 0.58, 1);
  }
  #blue {
    background: blue;
    left: 56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>
<div class="balls" id= "red"></div>
<div class="balls" id= "blue"></div>
```

## 使用贝塞尔曲线让运动更加自然

```html
<style>
  .balls {
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    top: 60%;
    animation-name: jump;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 25%;
    animation-timing-function: linear;
  }
  #blue {
    background: blue;
    left: 50%;
    animation-timing-function: ease-out;
  }
  #green {
    background: green;
    left: 75%;
    animation-timing-function: cubic-bezier(0.311, 0.441, 0.444, 1.649);
  }

  @keyframes jump {
    50% {
      top: 10%;
    }
  }
</style>
<div class="balls" id="red"></div>
<div class="balls" id="blue"></div>
<div class="balls" id="green"></div>
```

## 使用 audio 元素提高音频内容的可访问性

```html
<audio controls >
  <source src="https://s3.amazonaws.com/freecodecamp/screen-reader.mp3" type="audio/mpeg">
</audio>
```

## 将单选按钮包裹在 fieldset 元素中以获得更好的可访问性

```html
<fieldset>
    <legend>What level ninja are you?</legend>
    <input id="newbie" type="radio" name="levels" value="newbie">
    <label for="newbie">Newbie Kitten</label><br>
    <input id="intermediate" type="radio" name="levels" value="intermediate">
    <label for="intermediate">Developing Student</label><br>
    <input id="master" type="radio" name="levels" value="master">
    <label for="master">Master</label>
</fieldset>
```
## 使用 grid-template-columns 添加多列

```css
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```