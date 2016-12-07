---
title: Radio 单选框
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/radio?hidetitle=true
categories:
- Form
---


# Radio 单选框

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Radio 单选框，目前不支持验证，可以自定义通用属性class和style，以及picked（选中的值，需要加sync），value（radio的值），checked（是否选中），disabled（是否可以用），selectIcon（选中icon类名），noSelectIcon（未选中icon类名），iconStyles（icon样式），id（设置id的值）

            

## 如何使用

``` html
<template>
    <div>
        <div>尺寸</div>
        <Radio :picked.sync="message" value="L"></Radio>
        <Radio :picked.sync="message" value="XXL"></Radio>
    </div>
</template>
<script>
import { Radio } from 'mvui';
export default {
    components: {
        Radio,
    },
    data(){
        return {
            message: ''
        }
    }
} 
</script>
```




## API

Radio Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    picked      | 必填，选中的值               |    String          |       -       |       任意           |
|    value       | 必填，value的值            |    String          |      -         |  任意                |
|   checked      | 选填，选中的值             |    Boolean          |      false    |    true，false        |
|    disabled    | 选填，是否可用             |   Boolean           |     false      |true，false|
|    selectIcon  | 选填，选中icon 类名        |   String            |  mv-icon-round-radio |   所有icon类名   |
|    noSelectIcon| 选填， 未选中icon类名      |   String            | mv-icon-round |  所有icon类名  |
|    iconStyles  | 选填，icon样式            |   [String,Object]    |     -        |   任意         |
|    id          | 选填，id值                |   String           |     -     |   任意         |


Radio Events

|     事件名      | 说明                       |        返回值       | 
| :------------- |:-------------------------- | :----------------  |
|    on-change    |    属性发生变化时候触发     |        String (选中的值)         |



## 右侧示例代码


``` html

<template>
    <div class="body-wrapper">
        <Hometitle>Radio</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认</div>
                <div class="wrapper-area-content">
                    <div><Radio :picked.sync="message" value="测试2"></Radio></div>
                    <div><Radio :picked.sync="message" value="测试3"></Radio></div>
                </div>
                <div>{{ message }}</div>
            </div>

            <div class="wrapper-area">
                <div class="wrapper-area-title">不可用</div>
                <div class="wrapper-area-content">
                    <div>
                        <Radio :picked.sync="message" disabled :checked="true" value="测试1"></Radio>
                    </div>
                    <div>
                        <Radio :picked.sync="message" disabled value="测试1"></Radio>
                    </div>
                </div>
            </div>

            
            <div class="wrapper-area">
                <div class="wrapper-area-title">自定义icon</div>
                <div class="wrapper-area-content">
                    <div>
                        <Radio :picked.sync="name" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill"  :checked="true" value="测试2"></Radio>
                    </div>
                    <div>
                        <Radio :picked.sync="name" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill" value="测试4"></Radio>
                    </div>
                </div>
                <div>{{ name }}</div>
            </div>


            <div class="wrapper-area">
                <div class="wrapper-area-title">change事件</div>
                <div class="wrapper-area-content">
                    <div>
                        <Radio :picked.sync="test" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill"  :checked="true" value="测试8" @on-change="change"></Radio>
                    </div>
                    <div>
                        <Radio :picked.sync="test" no-select-icon="mv-icon-round-add" select-icon="mv-icon-round-add-fill" value="测试6" @on-change="change"></Radio>
                    </div>
                </div>
                <div>{{ test }}</div>
            </div>
    
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Radio,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Radio,
        Button
    },
    data() {
        return {
            message: '',
            name: '',
            test: ''
        }
    },
    methods: {
        change(test){
            console.log(test);
        }
    }
}
</script>

```
























