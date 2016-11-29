---
title: Circle 进度环
date: 2016-10-19 15:25:24
tags: http://localhost:8080/#!/circle?hidetitle=true
categories:
- Chart
---


# Circle 进度环

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
circle 可以自定义通用属性class和style，以及percent（百分比），size（进度换大小），strokeWidth（进度环宽度），strokeColor（进度环颜色），bgWidth（背景环宽度），bgColor（背景环颜色）


## 如何使用

``` html
<template>
   <Circle :percent.sync="10" :stroke-width="15" stroke-color="#ff4081"></Circle> 
</template>
<script>
import {
    Circle
} from 'mvui';
export default {
    components: {
        Circle,
    }
} 
</script>
```


## API

Circle props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    percent    | 必填，百分比                |    Num            |       0       |       0-100            |
|    size       | 选填，尺寸（单位rem）        |    Number          |      0.5       |  任意                |
|   stroke-width| 选填，进度环宽度             |    Number          |       10       |     任意            |
|stroke-color   | 选填，进度环颜色             |    String          |      #007aff   |    任意颜色        |
|stroke-linecap | 选填，环顶端形状             |   String           |      round    |round(圆)，square（方）|
|    bg-width   | 选填，背景环宽度             |    Number          |      10        |    任意数值        |
|    bg-color   | 选填，背景环颜色             |    String          |      #ecf1f4   |    任意颜色        |




## 右侧示例代码

### 默认形状
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Circle</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认cricle</div>
                <div class="wrapper-area-content">
                    <Circle :percent.sync="percent"></Circle>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">进度环顶端的形状</div>
                <div class="wrapper-area-content">
                    <Circle :percent.sync="percent" stroke-linecap="square"></Circle>
                    <Circle :percent.sync="percent" stroke-linecap="round"></Circle>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">背景环宽度、颜色</div>
                <div class="wrapper-area-content">
                    <Circle :percent.sync="percent" :bg-width="5" bg-color="#7a67ee"></Circle>
                    <Circle :percent.sync="percent" :bg-width="15" bg-color="#fd6131"></Circle>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">进度环宽度、颜色</div>
                <div class="wrapper-area-content">
                    <Circle :percent.sync="percent" :stroke-width="5" stroke-color="#10c0d8"></Circle>
                    <Circle :percent.sync="percent" :stroke-width="15" stroke-color="#ff4081"></Circle>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">进度环文本</div>
                <div class="wrapper-area-content">
                    <Circle :percent.sync="percent">
                        润度
                    </Circle>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">控制进度环</div>
                <div class="wrapper-area-content">
                    <div>
                        <Button @click="add" class="progress-btn-example" shape="round">增加</Button>
                        <Button @click="minus" class="progress-btn-example" shape="round">减少</Button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Circle,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Circle,
        Button
    },
    data() {
        return {
            percent: 10,
        }
    },
    methods: {
        add() {
            if (this.percent < 100) {
                this.percent = this.percent + 10;
            }
        },
        minus() {
            if (this.percent > 0) {
                this.percent = this.percent - 10;
            }
        }
    }
}
</script>
<style lang="less">
.click-btn {
    cursor: pointer;
}
</style>
```

