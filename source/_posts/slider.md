---
title: Slider 轮播
date: 2016-10-19 15:25:57
tags: https://greatboy.github.io/mvui-example/#!/slider?hidetitle=true
categories:
- Other
---


# Slider 轮播

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Slider 可以自定义通用属性class和style



## 如何使用

``` html
<template>  
    <Slider>
        <li>
            <img src="static/click1.jpg"/>
            <span>文案</span>
        </li>
        <li>
            <img src="static/click1.jpg"/>
            <span>文案</span>
        </li>
        <li>
            <img src="static/click1.jpg"/>
            <span>文案</span>
        </li>
        <li>
            <img src="static/click1.jpg"/>
            <span>文案</span>
        </li>
    </Slider>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Slider,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Button,
        Slider
    },
}
</script>
```


## API


Slider props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    direction  | 选填，滚动方式               |    String          |     y         |    x,y               |
|    bounce  | 选填，超出边界是否还能拖动    |    Boolean          |     true     |    true,false        |
|    prevent-default| 选填，是否阻止默认滚动事件 |    Boolean         |     true     |    true,false        |
|    disabled    | 选填，是否禁用              |    Boolean         |     false    |    true,false        |



## 右侧示例代码


### 默认
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Slider</Hometitle>
        <div class="wrapper-example wrapper-example-slider">
            <div class="wrapper-area-content" id="parent">
                <Slider>
                    <li>
                        <img src="static/click1.jpg"/>
                        <span>文案</span>
                    </li>
                    <li>
                        <img src="static/click1.jpg"/>
                        <span>文案</span>
                    </li>
                    <li>
                        <img src="static/click1.jpg"/>
                        <span>文案</span>
                    </li>
                    <li>
                        <img src="static/click1.jpg"/>
                        <span>文案</span>
                    </li>
                </Slider>
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Slider,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Button,
        Slider
    },
}
</script>
<style>
.wrapper-example-slider {
    width: 100%;
    top: 0px;
    left: 0px;
    box-sizing: border-box;
}

.wrapper-example-slider .wrapper-area-content {
    width: 100%;
}

.wrapper-example-slider .wrapper-area-content li {
    border-bottom: solid 1px #ccc;
    color: #666;
}

.wrapper-example-slider .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-slider .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>

```