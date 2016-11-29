---
title: 起步
date: 2016-10-19 15:23:10
tags:
categories:
- Summary
---


# 起步

## 使用之前

使用mvui之前，您应该了解vue.js的一些知识，其次需要了解rem布局，mvui基于rem布局


## Vue组件
基于Vue构建大型应用
以下概念贯穿iView前后，建议开发者花点时间来了解。
props 传递数据，以及:prop :prop.sync :prop.once的区别
slot 内容分发
events $emit @click 事件


## 安装 
$ npm install mvui --save


## 示例 
``` html
<template>  
    <div class="body-wrapper">
        <Icon class="ion-ionic" style="font-size: 0.18rem;color: blue;"></Icon>
    </div>
</template> 
<script>
    import { Icon } from 'mvui';
    export default{   
        components: { 
            Icon,
        }
    }
</script>
```

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串
###### 注意：变量需要在class前面加冒号（：）， 示例子
``` html
<Icon class="ion-ionic" style="font-size: 12px;"></Icon>
```


## rem布局

目前所有组件是基于rem布局，以320为基准，计算不同手机的font-size值进行缩放，适配不同的手机。这期间，您需要切不同的图片，可以切2倍图或者三倍图。建议所有页面的图片要切到3倍以上。

## rem布局原理

默认浏览器1rem=16px,也就相当于根元素html的字体大小为16px,当我们更改html font-size的时候，这时候rem也在跟着变化。
因此我们可以想象到当基础布局为320px的时候，1rem=16px的时候，320px=20rem，所以我们可以动态的计算获取到的可视区域宽度为windowWidth，windowWidth 与320 的比例值即为缩放比X。
公式为 windowWidth / 320 = X / 16,会有这样的一个公式。
当我们每次动态计算出X的值，把html font-size设置为x就可以满足需求。这个时候如果我们以320px布局的话，那么得做一次中间转换，当时我用fis写了一个插件，做中间转换。


后来去某一个公司面试，那公司老大给我提了个醒，他说为啥不可以直接以320px 直接等于3.2rem这种形式开发呢，就不存在了中间转化，他们只是差距 100倍，因此只需要在原来的公式计算出的x在乘以 100，既可以得出我们想要的结果。代码如下：
``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" id="viewport" content="width=320,user-scalable=no,initial-scale=1,minimum-scale=1,maximum-scale=1">
    <title></title>
    <link rel="shortcut icon" href="static/favicon.ico" type="image/x-icon">
    <style>
    * {
        padding: 0px;
        margin: 0px;
    }
    li,
    a {
        list-style: none;
        text-decoration: none;
        color: inherit;
    }
    body {
        padding: 0px;
        box-sizing: border-box;
    }
    .ui-tab {
        height: 10px;
    }
    </style>

    <link rel="stylesheet" type="text/css" href="static/weui.css"/>
    <link rel="stylesheet" type="text/css" href="static/index.css"/>
    <link rel="stylesheet" type="text/css" href="static/example.css"/>
    <script>
    (function(win) {
        var doc = win.document,
            html = doc.documentElement,
            scale = 16,
            resizeEvent = 'orientationchange' in window ? 'orientationchange' : 'resize';
        function calculate(){
            windowWidth = html && html.clientWidth || win.innerWidth;
            windowHeight = html && html.clientHeight || win.innerHeight;
            deviceAgent = navigator.userAgent.toLowerCase();
            scale = parseFloat(windowWidth / 3.2);
            // 修复微信2.3系统bug
            if (deviceAgent.match(/android\s*2.3/) && deviceAgent.match(/micromessenger/)) {
                scale = 16;
            }
            if( scale > 150 ){
                scale = 150;
            }
            html.style.fontSize = scale + 'px';
        }
        html.style.opacity = 0;   // 未渲染出来先把页面隐藏 
        win.addEventListener(resizeEvent, function() {
            calculate();
        }, false);
        doc.addEventListener('DOMContentLoaded', function() {
            calculate();
            body = doc.body;
            body.style.width = '3.2rem';
            body.style.fontSize = '0.13rem';
            body.style.margin = '0px auto';
            html.style.opacity = 1;
        }, false);
    })(window);
    </script>
</head>
<body>
    <div id="app"></div>
    <script src="dist/common.js"></script>
    <script src="dist/build.bundle.js"></script>
</body>
</html>

```

## rem布局步骤

###### 1) 把html js放到页面中
###### 2）把拿来的设计图改成320px宽度的像素，然后基于这个宽度进行测量大小。
###### 3）切图为320px基准的2倍数或者3倍图。
###### 4） 写代码了，也即是当我们测量为 100px的时候，我么只需要写1rem就可以。不做中间转换处理的好处是调试的时候可以直接在页面里调试。直接写rem就OK了









