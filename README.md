#### css-record

记录css一些使用技巧

* 本项目HTML文件都是移动端显示
* HTML 文件用来测试
* md 文件用来总结

* https://juejin.im/post/5dafc3df5188257a63539c64?utm_source=gold_browser_extension
* https://lucifer.ren/fe-interview/#/?id=%e7%ae%80%e5%8e%86-amp-%e4%b8%aa%e4%ba%ba%e4%b8%bb%e9%a1%b5-%f0%9f%93%96

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

* iOS和部分Android在使用 `button` 标签时，如果设置等高的 `line-height` ，会出现文字下偏移的情况
* iOS使用默认字体（不设置字体）时，奇数字号会出现上偏移1px的情况
* Android在 `字号 % 4 !== 0` 时（如11px，14px），会出现文字较大幅度上偏移的情况
* `字号 % 4 === 0` 时iOS和Android表现正常，不需要特殊处理
* 部分Android在smzdm webview内不支持12px以下的字号（会强制渲染为12px）

##### 解决方案
设置字体 `font-family: "PingFang SC", "Heiti SC", "San Francisco", "Helvetica";`
iOS
在iOS下，推荐使用 `button` 标签

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
        transform: scale(.25);
        transform-origin: 0 0;
    }
</style>
```

#### 怎么让页面变灰实现代码

```html
<style>  
html{  
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