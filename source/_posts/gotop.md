---
title: gotop 回到顶部
date: 2016-10-19 15:25:57
tags: https://greatboy.github.io/mvui-example/#!/gotop?hidetitle=true
categories:
- Other
---

# Gotop 回到顶部

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Gotop 可以自定义通用属性class和style，以及icon（icon类名），iconStyle（icon样式），height（距离多高显示），on-click（回调）



## 如何使用

``` html
<template>  
    <Gotop @on-click="gotopCallback"></Gotop>
</template>
<script>
    import { Gotop } from 'mvui';
    export default{   
        components: { 
            Gotop
        },
        methods: {
            gotopCallback(){
                console.dir('click');
            }
        }
    }
</script>
```


## API


Gotop props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    height     | 选填，滚动条多高显示          |    Numer          |     100         |    任意整数        |
|    icon       | 选填，图标类名               |    String          |mv-icon-arrow-top|    任意图标类名        |
|    iconStyle  | 选填，图标样式               |   [Object, String] |      -       |    任意               |


Gotop events

|     事件名      | 说明                       |        返回值       | 
| :------------- |:-------------------------- | :----------------  |
|    on-click    |    点击按钮时触发            |        event          |



## 右侧示例代码

### 回到顶部
``` html
<template>  
    <div class="body-wrapper">
        <Hometitle>Gotop</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">回到顶部</div>
                <div class="wrapper-area-content">
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                    <div>回到顶部</div>
                </div>
            </div>
            <Gotop @on-click="gotopCallback"></Gotop>
        </div>
    </div>
</template>
<script>
    import Hometitle from './common/hometitle.vue';
    import { Gotop } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Gotop
        },
        methods: {
            gotopCallback(e){
                console.dir('click');
            }
        }
    }
</script>
<style lang="less">
    .mv-btn{
        margin-top: 0.05rem;
    }
</style>
```



