---
title: Tip 提示
date: 2016-10-19 15:25:46
tags: http://localhost:8080/#!/tip?hidetitle=true
categories:
- View
---

# Tip 提示

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


``` html
<Tip class="mv-btn-primary" style="font-size: 0.14rem;"></Tip>
```


## 概述
Tip 提示框，可以自定义通用属性class和style，以及position（tip位置），show（是否显示），auto（是否自动关闭）


## 如何使用

直接在页面使用
``` html
<Tip :show.sync="true">我是提示内容</Tip>
```
动态的开启关闭,需要动态更改show变量（注意：需要加.sync，子组件变量的改变同步到父组件）
``` html
<Tip :show.sync="show">我是提示内容</Tip>
```


## API

Tip props

|     属性       | 说明                       |        类型       |    默认值          |    可选值              |
| :------------- |:-------------------------- | :----------------  | :------------   |    :--------------    |
|    class      | 选填，类名（可以设置icon）    |    String          |      -           |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -           |     任意               |
|    position   | 选填，显示位置               |    String          |       top        |      top,center,bottom|
|    show       | 选填，是否显示组件           |    Boolean          |      false      |   true,false          |
|    auto       | 选填，是否自动关闭           |    Boolean          |      true       |   true,false          |



## 右侧示例代码


### 顶部位置
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">顶部位置</div>
        <div class="wrapper-area-content">
            <div class="click-btn" @click="clickshow1">点击</div>
            <Tip :show.sync="show1" position="top">tip提示框 top 位置</Tip>
        </div>
    </div>
</template>
<script>
    import { Tip } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Tip
        },
        data(){
             return {
                show1: false,
             }
        },
        methods: {
            clickshow1(){
                this.show1 = true;
            }
        }
    }
</script>
<style lang="less">
    .click-btn{
        cursor: pointer;
    }
</style>
```




### 中间位置
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">中间位置</div>
        <div class="wrapper-area-content">
            <div class="click-btn" @click="clickshow2">点击</div>
            <Tip :show.sync="show2" position="center">tip提示框 center 位置</Tip>
        </div>
    </div>
</template>
<script>
    import { Tip } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Tip
        },
        data(){
             return {
                show2: false,
             }
        },
        methods: {
            clickshow2(){
                this.show2 = true;
            },
        }
    }
</script>
<style lang="less">
    .click-btn{
        cursor: pointer;
    }
</style>
```




### 底部位置
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">底部位置</div>
        <div class="wrapper-area-content">
            <div class="click-btn" @click="clickshow3">点击</div>
            <Tip :show.sync="show3" position="bottom">tip提示框 bottom 位置</Tip>
        </div>
    </div>
</template>
<script>
    import { Tip } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Tip
        },
        data(){
             return {
                show3: false,
             }
        },
        methods: {
            clickshow3(){
                this.show3 = true;
            },
        }
    }
</script>
<style lang="less">
    .click-btn{
        cursor: pointer;
    }
</style>
```





### 手动关闭
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">手动关闭</div>
        <div class="wrapper-area-content">
            <div class="click-btn" @click="clickshow4">显示tip</div>
            <div class="click-btn" @click="clickclose4">关闭tip</div>
            <Tip :show.sync="show4" position="center" :auto="false">tip提示框 center 位置</Tip>
        </div>
    </div>
</template>
<script>
    import { Tip } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Tip
        },
        data(){
             return {
                show4: false,
             }
        },
        methods: {
            clickshow4(){
                this.show4 = true;
            },
            clickclose4(){
                this.show4 = false;
            }
        }
    }
</script>
<style lang="less">
    .click-btn{
        cursor: pointer;
    }
</style>
```


        
