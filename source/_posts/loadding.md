---
title: loadding 加载图标
date: 2016-10-19 15:25:57
tags: http://localhost:8080/#!/loadding?hidetitle=true
categories:
- Other
---


# Loadding 加载图标

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Loadding 可以自定义通用属性class和style，以及show（是否显示），type（loadding呈现样式，circle 或 line），position（居中情况）


## 如何使用

``` html
<template>  
    <Loadding position="center" :show="show"></Loadding>
</template>
<script>
    import { Loadding } from 'mvui';
    export default{   
        components: { 
            Loadding,
        },
        data (){
            return {
                show: true
            }
        }
    }
</script>
```


## API


Loadding props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    type       | 选填，loadding样式          |    String          |     circle    |    circle,line        |
|    show       | 选填，是否显示loadding       |    Boolean          |      false  |    false,true        |
|    position  | 选填，图标位置               |     String          |      -       |    center               |


## 右侧示例代码


### 默认loadding
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">默认loadding</div>
        <div class="wrapper-area-content">
            <Loadding class="custome-loadding" :show="show"></Loadding>
        </div>
    </div>
</template>
<script>
    import { Loadding } from 'mvui';
    export default{   
        components: { 
            Loadding,
        },
        data (){
            return {
                show: true
            }
        }
    }
</script>
```


### 颜色
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">颜色</div>
        <div class="wrapper-area-content">
            <Loadding class="mv-loadding-primary" :show="show"></Loadding>
        </div>
    </div>
</template>
<script>
    import { Loadding } from 'mvui';
    export default{   
        components: { 
            Loadding,
        },
        data (){
            return {
                show: true
            }
        }
    }
</script>
```

### circle or line
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">circle or line</div>
        <div class="wrapper-area-content">
            <Loadding type="circle" :show="show"></Loadding>
            <Loadding type="line" :show="show"></Loadding>
        </div>
    </div>
</template>
<script>
    import { Loadding } from 'mvui';
    export default{   
        components: { 
            Loadding,
        },
        data (){
            return {
                show: true
            }
        }
    }
</script>
```


### 自定义
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">自定义</div>
        <div class="wrapper-area-content">
            <Loadding :show="show">
                <Icon class="ion-load-c circular" position="center"></Icon>
            </Loadding>
            <Loadding :show="show">
                <Icon class="ion-android-refresh circular"></Icon>
            </Loadding>
        </div>
    </div>
</template>
<script>
    import { Loadding,Icon } from 'mvui';
    export default{   
        components: { 
            Loadding,
            Icon
        },
        data (){
            return {
                show: true
            }
        }
    }
</script>
```


### 居中
``` html
<template>  
    <div class="wrapper-area">
        <div class="wrapper-area-title">居中</div>
        <div class="wrapper-area-content">
            <Loadding position="center" :show="show"></Loadding>
        </div>
    </div>
</template>
<script>
    import { Loadding } from 'mvui';
    export default{   
        components: { 
            Loadding,
        },
        data (){
            return {
                show: true
            }
        }
    }
</script>
```
        