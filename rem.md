
下面两种方案都是以设计稿为750来处理的
# 方案一


```js
function getRem () {
    var $html = document.querySelector('html');
    var oWidth = $html.clientWidth || document.documentElement.clientWidth;
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

# 方案二



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