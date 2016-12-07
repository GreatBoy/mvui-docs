---
title: Uploader 上传
date: 2016-10-19 15:25:57
tags: https://greatboy.github.io/mvui-example/#!/uploader?hidetitle=true
categories:
- Other
---


# Uploader 上传

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Uploader 可以自定义通用属性class和style，以及show（是否显示），type（loadding呈现样式，circle 或 line），position（居中情况）




## 如何使用

``` html
<template>  
    <Uploader url="http://www.huiyi.com/upload/upload" @on-preview="preview" @on-before="before" @on-validate="validate" @on-progress="progress"  @on-error="error" @on-success="success" @on-complete="complete"></Uploader>

</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Uploader,
} from 'mvui';
export default {
    components: {
        Uploader
    },
    data() {
        return {
            previewImage: ''
        }
    },
    methods: {
        preview(file){
            debugger;
            console.dir(arguments)
            this.previewImage = file[0];
        },
        validate(){
            debugger;
            console.dir(arguments)
        },
        before(){
            debugger;
            console.dir(arguments)
        },
        progress(){
            debugger;
            console.dir(arguments)
        },
        error(){
            debugger;
            console.dir(arguments)
        },
        success(){
            debugger;
            console.dir(arguments)
        },
        complete(){
            debugger;
            console.dir(arguments)
        }
    }
}
</script>
```


## API

Uploader props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名                  |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    url       | 必填， 上传地址               |    String          |      -        |    任意        |
|    field       | 选填，后台接受的field       |    String          |      file  |    任意        |
|    max-size    | 选填，文件最大尺寸（单位M）     |     Number          |      4       |    任意数字         |
|    max-size-message| 选填，文件最大尺寸（单位M） |     String      | 图片大小超过限制|    任意         |
|    type     | 选填，格式（用逗号隔开）     |     String          |      jpg,png,jpeg,gif       |    任意         |
|    type-message | 选填，格式错误提示      |     String      | 图片格式不正确          |    任意         |
|    auto-load | 选填，是否自动上传      |     Boolean      | true          |    true, false         |
|    more     | 选填，是否一次允许选中多张 |     Boolean      | true          |    true, false         |
|    status     | 选填，上传状态(更改run开始上传，上传后变complete)| String   |  'status'     |    run         |
   


## 右侧示例代码


### 默认loadding
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Uploader</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">单张图片</div>
                <div class="wrapper-area-content">
                    <Uploader url="http://www.huiyi.com/upload/upload" @on-preview="preview" @on-before="before" @on-validate="validate" @on-progress="progress"  @on-error="error" @on-success="success" @on-complete="complete"></Uploader>
                    <img style="width: 40px;" :src="previewImage"/>
                </div>
            </div>

            <div class="wrapper-area">
                <div class="wrapper-area-title">多张图片</div>
                <div class="wrapper-area-content">
                    <Uploader url="http://www.huiyi.com/upload/upload" @on-preview="preview1" @on-before="before1" @on-validate="validate1" @on-progress="progress1"  @on-error="error1" @on-success="success1" @on-complete="complete1" :more="true"></Uploader>
                    <div v-for="item in previewImage1">
                        <img style="width: 40px;" :src="item"/>
                    </div>
                </div>
            </div>

        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Uploader
} from 'mvui';
export default {
    components: {
        Hometitle,
        Uploader
    },
    data() {
        return {
            previewImage: '',
            previewImage1: []
        }
    },
    methods: {
        preview(file){
            debugger;
            console.dir(arguments)
            this.previewImage = file[0];
        },
        validate(){
            debugger;
            console.dir(arguments)
        },
        before(){
            debugger;
            console.dir(arguments)
        },
        progress(){
            debugger;
            console.dir(arguments)
        },
        error(){
            debugger;
            console.dir(arguments)
        },
        success(){
            debugger;
            console.dir(arguments)
        },
        complete(){
            debugger;
            console.dir(arguments)
        },
        preview1(file){
            debugger;
            console.dir(arguments)
            this.previewImage1 = file;
        },
        validate1(){
            debugger;
            console.dir(arguments)
        },
        before1(){
            debugger;
            console.dir(arguments)
        },
        progress1(){
            debugger;
            console.dir(arguments)
        },
        error1(){
            debugger;
            console.dir(arguments)
        },
        success1(){
            debugger;
            console.dir(arguments)
        },
        complete1(){
            debugger;
            console.dir(arguments)
        }
    }
}
</script>
<style>
.wrapper-example-load-scroll {
    position: fixed;
    width: 100%;
    height: 100%;
    padding-top: 0.45rem;
    top: 0px;
    left: 0px;
    box-sizing: border-box;
}

.wrapper-example-load-scroll .wrapper-area-content {
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.wrapper-example-load-scroll .wrapper-area-content li {
    height: 0.4rem;
    line-height: 0.4rem;
    border-bottom: solid 1px #ccc;
    padding-left: 0.1rem;
    color: #666;
}

.wrapper-example-load-scroll .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-load-scroll .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>
```


