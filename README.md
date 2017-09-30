# px to rem

> webpack-px-to-rem + scss-loader + vue-cli

## 配置

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

```
## device resize doc.documentElement 代码

``` bash
(function(win) {
  var doc = win.document
  var docEl = doc.documentElement
  var tid

  function refreshRem() {
    var width = docEl.getBoundingClientRect().width
    if (width > 750) {
      docEl.style.fontSize = '20px'
    } else {
      var rem = 40 * width / 750
      docEl.style.fontSize = rem + 'px'
    }
  }

  win.addEventListener('resize', function() {
    clearTimeout(tid)
    tid = setTimeout(refreshRem, 300)
  }, false)

  win.addEventListener('pageshow', function(e) {
    if (e.persisted) {
      clearTimeout(tid)
      tid = setTimeout(refreshRem, 300)
    }
  }, false)

  refreshRem()

})(window)
```

## 链接

> webpack-px-to-rem <a href='https://www.npmjs.com/package/webpack-px-to-rem'>使用说明</a>

