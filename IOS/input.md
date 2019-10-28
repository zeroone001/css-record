1. IOS键盘字母输入,默认首字母大写的解决方案

```html
<input autocapitalize="off" autocorrect="off" autocomplete="off" />

```
2. 关于iOS与OS X端字体的优化(横竖屏会出现字体加粗不一致等)问题
```css
-webkit-text-size-adjust: 100%;
-ms-text-size-adjust: 100%;
text-size-adjust: 100%;
```

3. 某些情况下非可点击元素如(label,span)监听click事件,ios下不会触发

```css
cursor: pointer;
```
4. iOS(safari)标签绑定点击事件无效

```html
<a onclick="">
```

5. ios中location.href跳转页面空白
```javascript
setTimeout(() => {
       window.location.href = 'www.juejin.im'
}, 0);
```
6. 键盘弹起下落时的bug解决方法
```javascript
function handleFocusout () {
    document.addEventListener('foucusout', () => {
        document.body.scrollTop = 0;
    });
}
function handleResize () {
    let startHeight = document.documentElement.clientHeight;
    window.addEventListener('resize', () => {
        if (document.activeElement.tagName === 'INPUT') {
            setTimeout(() => {
                document.activeElement.scrollIntoView();
            }, 0);
        }

        // 解决fixed元素被顶起的问题
        let nowHeight = document.documentElement.clientHeight;
        if (startHeight > nowHeight) {
            ele.style.display = 'none';
        } else {
            ele.style.display = 'block';
        }
    });

}
```