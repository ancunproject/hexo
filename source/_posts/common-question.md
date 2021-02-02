---
title: "常见小问题"
author: "Luo"
categories: notes
tags: [js,css]
description: '列举记录工作中遇到的一些代码'
image: city-3.jpg
---

##### 1. 判断操作系统js

```
let u = navigator.userAgent
if (u.indexOf('Android') > -1 || u.indexOf('Adr') > -1) {
  window.android.closePage(this.contractInfo.contractNo);
}
if (u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/)) {
  window.webkit.messageHandlers.closePage.postMessage(this.contractInfo.contractNo);
}
```

##### 2. 切换

```
function tabs(tabTit, on, tabCon) {
    $(tabCon).each(function () {
        $(this).children().eq(0).show();
    });
    $(tabTit).each(function () {
        $(this).children().eq(0).addClass(on);
    });
    $(tabTit).children().click(function () {
        $(this).addClass(on).siblings().removeClass(on);
        var index = $(tabTit).children().index(this);
        $(tabCon).children().eq(index).show().siblings().hide();
    });
}
tabs(".ul-1", "current", ".ul-2")
```

##### 3. 映射

```
1. return {
	'1': '自然人',
    '2': '法人'
} [this.user.identity]
or
2. let map = {
    1: '自然人',
    2: '法人'
}
return map[val] ? map[val] : '未知'
```



##### 4.不常见样式设置

修复行内图片默认样式

```
img {
	display: inline-block;
	margin: 0;
}
```

彩虹滚动条，仅对Chrome系浏览器生效

```
::-webkit-scrollbar {
    width: 3px;
    height: 3px;
}
::-webkit-scrollbar-thumb {
	background-image: linear-gradient(45deg, Cyan 0%, Magenta 50%, Yellow 100%);
}
```

选中字体颜色

```
::selection {
    color: White;
    background: Black;
}
```

