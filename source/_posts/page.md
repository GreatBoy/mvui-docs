---
title: Page 分页
date: 2016-10-19 15:25:57
tags: http://localhost:8080/#!/page?hidetitle=true
categories:
- Other
---


# Page 分页

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Page 分页 可以自定义通用属性class和style，以及current（当前页），all（总页数）




## 如何使用

``` html
<template>  
    <div>
        <Page :current="current" :all="all" @on-change="change"></Page>
    </div>
</template>
<script>
    import { Page } from 'mvui';
    export default{   
        components: { 
            Page,
        },
        data (){
            return {
                current: 1,
                all: 10
            }
        }
    }
</script>
```



## API


Page props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    current    | 必填，当前页                 |    Number          |     1        |    大于0整数               |
|    all       | 必填，总页数                  |    Number          |     1       |    大于0整数                |


Page Events


Gotop events

|     事件名      | 说明                       |        返回值       | 
| :------------- |:-------------------------- | :----------------  |
|    on-change    |    点击上一页下一页触发     |        Number(切换后的页面)|


## 右侧示例代码


### 默认loadding
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Page</Hometitle>
        <div class="wrapper-example wrapper-example-page">
            <div class="wrapper-area-content" id="parent">
                <Page :current="current" :all="all" @on-change="change"></Page>
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Button,
    Page
} from 'mvui';
export default {
    components: {
        Hometitle,
        Button,
        Page
    },
    data() {
        return {
            current: 1,
            all: 10
        }
    },
    methods: {
        change: function(page){
            console.dir(page);
        }
    }
}
</script>
<style lang="less">
.wrapper-example-page {
    position: fixed;
    width: 100%;
    height: 100%;
    padding-top: 0.45rem;
    top: 0px;
    left: 0px;
    box-sizing: border-box;

    .wrapper-area-content {
        width: 100%;
        height: 100%;
        overflow: hidden;
        text-align: center;
    }
    .wrapper-area-content li {
        height: 0.4rem;
        line-height: 0.4rem;
        border-bottom: solid 1px #ccc;
        padding-left: 0.1rem;
        color: #666;
    }
    .wrapper-area-content li:last-child {
        border-bottom-width: 0px;
    }

    .wrapper-area-content .wrapper-area {
        padding: 0px;
        margin: 0px;
    }
}
</style>
```


