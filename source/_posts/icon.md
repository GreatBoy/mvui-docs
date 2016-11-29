---
title: Icon 图标
date: 2016-10-18 17:25:16
tags: 
- http://localhost:8080/#!/icon?hidetitle=true
categories:
- Basic
---




# Icon 图标

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
icon 图标尽量选用常用的图标，由于项目中自定义的图标比较多，因此框架不提供更多的图标，
自己可以用自己的图标，这里图标来源于iconfont，在此感谢[iconfont](http://www.iconfont.cn/)，感谢国内的大公司能做出这么多优秀的开源框架和工具。


## 如何使用
使用Icon组件只需要指定图标的class即可，示例代码

``` html
<Icon class="mv-icon-add"></Icon>
```
渲染后为

``` html
<i class="mvfont mv-icon-add"></i>
```


## API

Icon Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意icon类        |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |



## 右侧示例代码

``` html
<template>  
    <div class="body-wrapper icon-wrapper wrapper-example-icon">
        <Hometitle>Icon</Hometitle>
        <div class="wrapper-example">
            <li>
                <Icon class="mv-icon-arrow-down-c"></Icon>
                <br/>
                <span>mv-icon-arrow-down-c</span>
            </li>
            <li>
                <Icon class="mv-icon-arrow-up-c"></Icon>
                <br/>
                <span>mv-icon-arrow-up-c</span>
            </li>
            <li>
                <Icon class="mv-icon-add"></Icon>
                <br/>
                <span>mv-icon-add</span>
            </li>
            <li>
                <Icon class="mv-icon-reduce"></Icon>
                <br/>
                <span>mv-icon-reduce</span>
            </li>
            <li>
                <Icon class="mv-icon-round-add"></Icon>
                <br/>
                <span>mv-icon-round-add</span>
            </li>
            <li>
                <Icon class="mv-icon-round-add-fill"></Icon>
                <br/>
                <span>mv-icon-round-add-fill</span>
            </li>
            <li>
                <Icon class="mv-icon-round-close"></Icon>
                <br/>
                <span>mv-icon-round-close</span>
            </li>
            <li>
                <Icon class="mv-icon-round-close-fill"></Icon>
                <br/>
                <span>mv-icon-round-close-fill</span>
            </li>
            <li>
                <Icon class="mv-icon-square-check"></Icon>
                <br/>
                <span>mv-icon-square-check</span>
            </li>
            <li>
                <Icon class="mv-icon-square"></Icon>
                <br/>
                <span>mv-icon-square</span>
            </li>
            <li>
                <Icon class="mv-icon-square-check-fill"></Icon>
                <br/>
                <span>mv-icon-square-check-fill</span>
            </li>
            <li>
                <Icon class="mv-icon-notification"></Icon>
                <br/>
                <span>mv-icon-notification</span>
            </li>
            <li>
                <Icon class="mv-icon-notificationfill"></Icon>
                <br/>
                <span>mv-icon-notificationfill</span>
            </li>
            <li>
                <Icon class="mv-icon-round-check-fill"></Icon>
                <br/>
                <span>mv-icon-round-check-fill</span>
            </li>
            <li>
                <Icon class="mv-icon-round"></Icon>
                <br/>
                <span>mv-icon-round</span>
            </li>
            <li>
                <Icon class="mv-icon-round-radio"></Icon>
                <br/>
                <span>mv-icon-round-radio</span>
            </li>
            <li>
                <Icon class="mv-icon-favor"></Icon>
                <br/>
                <span>mv-icon-favor</span>
            </li>
            <li>
                <Icon class="mv-icon-favor-fill"></Icon>
                <br/>
                <span>mv-icon-favor-fill</span>
            </li>
            <li>
                <Icon class="mv-icon-close"></Icon>
                <br/>
                <span>mv-icon-close</span>
            </li>
            <li>
                <Icon class="mv-icon-check"></Icon>
                <br/>
                <span>mv-icon-check</span>
            </li>
            <li>
                <Icon class="mv-icon-caret-top"></Icon>
                <br/>
                <span>mv-icon-caret-top</span>
            </li>
            <li>
                <Icon class="mv-icon-caret-right"></Icon>
                <br/>
                <span>mv-icon-caret-right</span>
            </li>
            <li>
                <Icon class="mv-icon-caret-left"></Icon>
                <br/>
                <span>mv-icon-caret-left</span>
            </li>
            <li>
                <Icon class="mv-icon-caret-bottom"></Icon>
                <br/>
                <span>mv-icon-caret-bottom</span>
            </li>
            <li>
                <Icon class="mv-icon-arrow-top"></Icon>
                <br/>
                <span>mv-icon-loading-3</span>
            </li>
            <li>
                <Icon class="mv-icon-arrow-bottom"></Icon>
                <br/>
                <span>mv-icon-loading-4</span>
            </li>
            <li>
                <Icon class="mv-icon-arrow-left"></Icon>
                <br/>
                <span>mv-icon-arrow-left</span>
            </li>
            <li>
                <Icon class="mv-icon-arrow-right"></Icon>
                <br/>
                <span>mv-icon-arrow-right</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-1"></Icon>
                <br/>
                <span>mv-icon-loading-1</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-2"></Icon>
                <br/>
                <span>mv-icon-loading-2</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-3"></Icon>
                <br/>
                <span>mv-icon-loading-3</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-4"></Icon>
                <br/>
                <span>mv-icon-loading-4</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-5"></Icon>
                <br/>
                <span>mv-icon-loading-5</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-6"></Icon>
                <br/>
                <span>mv-icon-loading-2</span>
            </li>
            <li>
                <Icon class="mv-icon-loading-7"></Icon>
                <br/>
                <span>mv-icon-loading-7</span>
            </li>
            <li>
                <Icon class="mv-icon-home"></Icon>
                <br/>
                <span>mv-icon-home</span>
            </li>
        </div>
    </div>
</template> 
<script>
    import Hometitle from './common/hometitle.vue';
    import { Icon } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Icon,
        },
        data(){
            return {
                test: {
                    'font-size': '12px',
                    'color': 'red'
                }
            }
        }
    }
</script>
<style lang="less">
    .wrapper-example-icon .wrapper-example{
        li{
            box-sizing: border-box;
            -webkit-box-sizing: border-box;
            width: 25%;
            color: #5e6d82;
            float: left;
            text-align: center;
            border-right: 1px solid #eee ;
            border-bottom: 1px solid #eee ;
            background: white;
            height: 0.9rem;
            padding: 0.1rem 0px;
            &:nth-child(4n+4){
                border-right: 0px;
            }
            span{
                font-size: 0.11rem;
            }
        }
    }
</style>
```









