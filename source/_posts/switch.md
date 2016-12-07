---
title: Switch 开关
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/switch?hidetitle=true
categories:
- Form
---


# Switch 开关

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Switch 开关，目前不支持验证，可以自定义通用属性class和style，以及checked（开关，是否开关），disabled（是否可用）


            
## 如何使用

``` html
<template>
    <Switch :checked.sync="selected"></Switch>
</template>
<script>
import { Switch } from 'mvui';
export default {
    components: {
        Switch,
    },
    data(){
        return {
            selected: false
        }
    }
} 
</script>
```


## API

Switch Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    checked      | 必填，设置开关              |    Boolean       |       false       |       true | false    |
|    disabled     | 选填，是否可用             |    Boolean          |      false        |  true | false     |


Switch Slot

|     name名称       | 说明                       
| :------------- |:-------------------------- 
|    open      | 选填，开
|    close      | 选填，关



 

## 右侧示例代码


``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Switch</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">slot显示</div>
                <div class="wrapper-area-content">
                    <span>开关</span>
                    <Switch :checked.sync="selected1">
                        <span slot="open">开</span>
                        <span slot="close">关</span>
                    </Switch>
                </div>
                <div>{{ selected1 }}</div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认</div>
                <div class="wrapper-area-content">
                    <span>选择姓名</span>
                    <Switch :checked.sync="selected2"></Switch>
                </div>
                <div>{{ selected2 }}</div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">是否可用</div>
                <div class="wrapper-area-content">
                    <span>选择姓名</span>
                    <Switch :checked.sync="selected3" :disabled="true"></Switch>
                </div>
                <div>{{ selected3 }}</div>
            </div>
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Switch,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Switch,
        Button
    },
    data() {
        return {
            selected1: true,
            selected2: true,
            selected3: true
        }
    }
}
</script>
```


