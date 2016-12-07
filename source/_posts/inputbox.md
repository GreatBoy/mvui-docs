---
title: Inputbox 输入框
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/inputbox?hidetitle=true
categories:
- Form
---


# Inputbox 输入框

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
inpubox 输入框，目前不支持验证，可以自定义通用属性class和style，以及value（value值，需要加sync），type（输入框type类型），placeholder（placeholder），closeIcon（是否显示清楚icon）


            

## 如何使用

``` html
<template>
    <Inputbox :value.sync="name"></Inputbox>
</template>
<script>
import { Inputbox } from 'mvui';
export default {
    components: {
        Inputbox,
    }
} 
</script>
```



## API

Inputbox Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    value      | 必填，value值               |    String          |       -       |       任意           |
|    type       | 选填，input type类型        |    String          |      text         |  任意                |
|   placeholder | 选填，placeholder          |    String          |      -          |    任意        |
|    closeIcon  | 选填，是否显示清除icon       |   Boolean           |     true     |true，false|

 

## 右侧示例代码


``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Inputbox</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认</div>
                <div class="wrapper-area-content">
                    <div>姓名：</div>
                    <Inputbox :value.sync="name"></Inputbox>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">修改样式</div>
                <div class="wrapper-area-content">
                    <div>姓名：</div>
                    <Inputbox :value.sync="name" style="border: solid 1px #ccc;border-radius: 0.03rem;width: 100%;text-indent: 0.1rem;"></Inputbox>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">动态数据</div>
                <div class="wrapper-area-content">
                    <div>消息：</div>
                    <Inputbox :value.sync="message" style="border: solid 1px #ccc;border-radius: 0.03rem;width: 100%;"></Inputbox>
                </div>
                <div>消息：{{ message }}</div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">placeHolder</div>
                <div class="wrapper-area-content">
                    <div>爱好：</div>
                    <Inputbox :value.sync="like" placeholder="请输入爱好" :close-icon="false" style="border: solid 1px #ccc;border-radius: 0.03rem;width: 100%;"></Inputbox>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Inputbox,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Inputbox,
        Button
    },
    data() {
        return {
            name: ' ',
            message: '',
            like: ''
        }
    }
}
</script>

```
























