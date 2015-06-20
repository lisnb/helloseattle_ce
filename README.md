hello seattle
=======

**因为Google商店的开发者账号验证起来比较麻烦，所以目前只能在开发者模式下，装在Chrome里使用额**

======

###使用方法
1. 右上角点击“菜单” -> “更多工具” -> “扩展程序”
2. 在上面把“开发者模式”前面复选框打勾勾
3. “加载正在开发的扩展程序”， 找到这个repo下的helloseattle文件夹，确定
4. 可以使用了

###配置方法
鉴于直接使用源代码安装了，就直接改源代码配置

####配置要跳转到的的页面
在 ./helloseattle.js 中， *url*指要跳转到的网址，默认为leetcode，因为我第二遍还没刷完 ^_^

```javascript
var helloseattle = {
    url: "https://leetcode.com/problemset/algorithms/",
    redirect:function(){
        alert("你女票等着你呢，看你麻痹，刷题去！");
        alert("快去啊！")
        window.location.href = helloseattle.url;
    }
}

helloseattle.redirect();
```


####配置要block的网站
在./manifest.json中

```json
"content_scripts": [{
        "css": ["helloseattle.css"],
        "js": ["helloseattle.js"],
        "matches": ["http://*.bilibili.com/*","http://*.acfun.tv/*","http://*.weibo.com/*","http://*.facebook.com/*","http://*.twitter.com/*","http://*.youtube.com/*"]
}]
```

matches 列表里包含了所有要被block的网址，可以酌情添加，表达式的具体用法可以参见 https://developer.chrome.com/extensions/match_patterns 

=======

祝刷题愉快 …^_^…
