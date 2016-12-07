---
title: Selector 选择框
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/selector?hidetitle=true
categories:
- Form
---


# Selector 选择框

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Selector 输入框，目前不支持验证，可以自定义通用属性class和style，以及selected（selected选中的值，需要加sync），placeholder（placeholder），options（option的值），disabled（disabled是否可用），arrowIcon（选择箭头icon），iconStyle（icon样式）

            

## 如何使用

``` html
<template>
    <Selector :selected.sync="selected" :options="option"></Selector>
</template>
<script>
import { Selector } from 'mvui';
export default {
    components: {
        Selector,
    },
    data(){
        return {
            selected: "2",
            option: [
                {
                    label: '北京',
                    value: '1'
                },
                {
                    label: '南京',
                    value: '2',
                }
            ]
        }
    }
} 
</script>
```




## API

Selector props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    selected   | 必填，选中的值               |    String          |       -       |     任意             |
|   placeholder | 选填，placeholder          |    String          |      -          |    任意        |
|    options    | 必填，结构[{label:'',value:''}]|    Array          |      -         |  任意                |
|    disabled   | 选填，是否失效              |   Boolean           |     false     |      true，false|
|    arrow-icon   | 选填，图标class          |   String           | mv-icon-arrow-bottom|     任何icon类名   |
|    icon-style   | 选填，icon样式          |   [String, Object]   |        -        |     任何icon样式   |




Selector Events

|     事件名      | 说明                       |        返回值       | 
| :------------- |:-------------------------- | :----------------  |
|    on-change    |    属性发生变化时候触发     |     String(选中的值)|



## 右侧示例代码


``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Selector</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认</div>
                <div class="wrapper-area-content">
                    <span>选择省</span>
                    <Selector :selected.sync="selected" :options="option"></Selector>
                </div>
                <div>{{ selected }}</div>
            </div>

            <div class="wrapper-area">
                <div class="wrapper-area-title">失效</div>
                <div class="wrapper-area-content">
                    <span>选择省</span>
                    <Selector :selected.sync="testSelected" :disabled="true" placeholder="选择省" :options="testOption"></Selector>
                </div>
            </div>

            <div class="wrapper-area">
                <div class="wrapper-area-title">更改Icon</div>
                <div class="wrapper-area-content">
                    <span>选择省</span>
                    <Selector :selected.sync="testSelected" placeholder="选择省" arrow-icon="mv-icon-caret-bottom" :options="testOption"></Selector>
                </div>
            </div>


            <div class="wrapper-area">
                <div class="wrapper-area-title">change事件</div>
                <div class="wrapper-area-content">
                    <span>选择省</span>
                    <Selector :selected.sync="changeSelect" @on-change="change" placeholder="选择省" arrow-icon="mv-icon-caret-bottom" :options="changeOption"></Selector>
                </div>
            </div>

        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Selector,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Selector,
        Button
    },
    data() {
        return {
            selected: "2",
            option: [
                {
                    label: '北京',
                    value: '1'
                },
                {
                    label: '南京',
                    value: '2',
                }
            ],
            testSelected: '',
            testOption: [
                {
                    label: '北京',
                    value: '1'
                },
                {
                    label: '南京',
                    value: '2',
                }
            ],
            changeSelect: '',
            changeOption: [
                {
                    label: '北京',
                    value: '1'
                },
                {
                    label: '南京',
                    value: '2',
                }
            ]

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
























