---
title: Checkbox 多选框
date: 2016-10-19 15:25:24
tags: http://localhost:8080/#!/inputbox?hidetitle=true
categories:
- Form
---


# Checkbox 多选框

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Checkbox 多选框，目前不支持验证，可以自定义通用属性class和style，以及picked（选中的值，需要加sync），value（checkbox value的值），checked（是否选中），disabled（是否可以用），selectIcon（选中icon类名，默认ion-ios-checkmark），noSelectIcon（未选中icon类名，默认ion-ios-circle-outline），iconStyles（icon样式），id（设置id的值）


            

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

Checkbox Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    picked      | 必填，选中的值               |    String          |       -       |       任意           |
|    value       | 必填，value的值            |    String          |      -         |  任意                |
|   checked      | 选填，选中的值             |    Boolean          |      false    |    true，false        |
|    disabled    | 选填，是否可用             |   Boolean           |     false      |true，false|
|    selectIcon  | 选填，选中icon 类名        |   String            |  ion-ios-checkmark |   所有icon类名   |
|    noSelectIcon| 选填， 未选中icon类名      |   String            | ion-ios-circle-outline |  所有icon类名  |
|    iconStyles  | 选填，icon样式            |   [String,Object]         |     -        |   任意         |
|    id          | 选填，id值                |   String           |     -     |   任意         |


Checkbox Events

|     事件名      | 说明                       |        返回值       | 
| :------------- |:-------------------------- | :----------------  |
|    on-change    |    属性发生变化时候触发     |        Array (选中的值)         |



## 右侧示例代码

``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Checkbox</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认</div>
                <div class="wrapper-area-content">
                    <span>选择姓名</span>
                    <Checkbox :picked.sync="message" value="张三"></Checkbox>
                    <Checkbox :picked.sync="message" value="李四"></Checkbox>
                    <Checkbox :picked.sync="message" value="王五"></Checkbox>
                </div>
                <div>{{ message }}</div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">失效</div>
                <div class="wrapper-area-content">
                    <span>选择男女</span>
                    <Checkbox :picked.sync="sex" disabled :checked="true" value="男"></Checkbox>
                    <Checkbox :picked.sync="sex" disabled value="女"></Checkbox>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">change事件</div>
                <div class="wrapper-area-content">
                    <span>选择基友</span>
                    <Checkbox :picked.sync="hobby" value="妹子" ></Checkbox>
                    <Checkbox :picked.sync="hobby" value="哥哥" ></Checkbox>
                    <Checkbox :picked.sync="hobby" value="小三" ></Checkbox>
                </div>
                <div>{{ hobby }}</div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">自定义icon</div>
                <div class="wrapper-area-content">
                    <span>选择</span>
                    <Checkbox :picked.sync="test" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill" value="test1" ></Checkbox>
                    <Checkbox :picked.sync="test" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill" value="test2" ></Checkbox>
                    <Checkbox :picked.sync="test" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill" value="test3" ></Checkbox>
                </div>
                <div>{{ hobby }}</div>
            </div>

        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Checkbox,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Checkbox,
        Button
    },
    data() {
        return {
            message: [],
            hobby: [],
            sex: [],
            test: []
        }
    },
    methods: {
        change(val){
            console.dir(val);
            debugger;
        }
    }
}
</script>


```
























