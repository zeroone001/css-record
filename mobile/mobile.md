1. ios防止长按页面元素被选中
   ```css
   * {
        -webkit-touch-callout:none; 
        -webkit-user-select:none;
        -khtml-user-select:none; 
        -moz-user-select:none;
        -ms-user-select:none;
        user-select:none;
    }
   ```
2. html5碰到上下拉动滚动条时卡顿/慢怎么解决
   ```css
   .scroll-box {
       height: 100%;
       overflow-y: auto;
       -webkit-overflow-scrolling: touch;
       overflow-scrolling: touch;
   }
   ```
3. 浏览器后退不刷新
```javascript
// 方法1：
window.addEventListener('pageshow', () => {
  if (e.persisted || (window.performance && 
    window.performance.navigation.type == 2)) {
    location.reload()
  }
}, false);
// 方法2:
window.history.replaceState(null, '', window.location.href + '?timestamp=' + new Date().getTime());
```   




