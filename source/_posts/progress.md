---
title: Progress 进度条
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/progress?hidetitle=true
categories:
- Chart
---


# Progress 进度环

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
progress 可以自定义通用属性class和style，以及percent（百分比），size（进度换大小），strokeWidth（进度环宽度），strokeColor（进度环颜色），bgWidth（背景环宽度），bgColor（背景环颜色）


## 如何使用

``` html
<template>
    <Progress :percent.sync="percent"></Progress>
</template>
<script>
import { Progress } from 'mvui';
export default {
    components: {
        Progress,
    }
} 
</script>
```




## API

Progress props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    percent    | 必填，百分比                |    Num            |       0       |       0-100            |
|    height     | 选填，进度条高度            |    Number          |      0.1（rem）  |  任意                |
|   stroke-color| 选填，进度环颜色             |    String          |      #007aff   |    任意颜色        |
|    shape      | 选填，进度条形状             |   String           |      round    |round(圆)，square（方）|
|    bg-color   | 选填，背景环颜色             |    String          |      #f3f3f3   |    任意颜色        |



## 右侧示例代码


``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Progress</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认进度条</div>
                <div class="wrapper-area-content">
                    <Progress :percent.sync="percent"></Progress>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">高度</div>
                <div class="wrapper-area-content">
                    <Progress :percent.sync="percent" :height="0.05" class="my-progress"></Progress>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">颜色</div>
                <div class="wrapper-area-content">
                    <Progress :percent.sync="percent" stroke-color="#23d089" class="my-progress"></Progress>
                    <Progress :percent.sync="percent" bg-color="#cddc39" class="my-progress"></Progress>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">更改进度</div>
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
    Progress,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Progress,
        Button
    },
    data() {
        return {
            percent: 10
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
.progress-btn-example {
    padding: 0.03rem 0.5rem;
}
</style>

```
























