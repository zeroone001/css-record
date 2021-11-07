# rem 

下面两种方案都是以设计稿为750来处理的

## 原理

### 准备

首先我们要记住一个公式， x(rem) * (html的fontSize) = 真实px

```js
const $html = document.querySelector('html');
const oWidth = $html.clientWidth || document.documentElement.clientWidth;
```
oWidth 为真实的屏幕宽度


### 开始

打个比方，把整个屏幕分为100份，当然这里10份，20份都行

这里我们也要把设计稿分为100份

那么，就像是上面说的似的， `oWidth/100 === 750/100` （750 就是指设计稿的尺寸）


那么：

x 就是我们要求的rem的值

1. 真实px = oWidth/100 * x (rem)
2. 设计稿真实px = 750/100 * x(rem)

最后，设计稿真实px 是已知的， 最后的计算公式， `x(rem) = 设计稿真实px/750 * 100`

```scss
$ue-width: 750; /* ue图的宽度 */

@function px2rem ($px) {
    @return #{$px/$ue-width * 100}rem;
}
```

## 方案一

这里方案一是分为了10份，所以最后的计算公式没有 *10

```js
function getRem () {
    const $html = document.querySelector('html');
    const oWidth = $html.clientWidth || document.documentElement.clientWidth;
    if (oWidth > 1024) {
        $html.style.fontSize = 1024 / 10 + 'px';
    } else {
        $html.style.fontSize = oWidth / 10 + 'px';
    }
}
getRem();
window.onresize = getRem;
```

```css 
@function px2rem($px) {
    @return $px / 75 * 1rem;
}
```

## 方案二



```js
export default {
    beforeMount () {
        this.filterRem();
        window.onresize = this.filterRem;
    },
    methods: {
        filterRem () {
            let deviceWidth = document.documentElement.clientWidth;
            if (deviceWidth > 1024) deviceWidth = 1024;
            document.documentElement.style.fontSize = deviceWidth / 750 * 100 + 'px';
        }
    }
};
```

```css
@function rem ($px) {
    @return $px / 100 * 1rem;
} 
```