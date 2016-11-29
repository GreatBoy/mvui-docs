---
title: Scroll 滚动条
date: 2016-10-19 15:25:57
tags: http://localhost:8080/#!/scroll?hidetitle=true
categories:
- Other
---


# Scroll 滚动条

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Scroll 可以自定义通用属性class和style，以及size（滚动距离），direction（滚动方式y轴|x轴），isMomentum（惯性）
，isBounce（超出边界是否可拖动），bounceTime（回弹时间），preventDefault（是否阻止默认行为），disabled（是否禁用），
pullRefresh（下拉刷新），refreshStatus（刷新状态），isRefresh（是否从新计算）



## 如何使用

``` html
<template>  
    <div>
        <Scroll>
            <ul>
                <li>滚动测试</li>
                <li>滚动测试</li>
                <li>滚动测试</li>
                <li>滚动测试</li>
            </ul>
        </Scroll>
    </div>
</template>
<script>
    import { Scroll } from 'mvui';
    export default{   
        components: { 
            Scroll,
        }
    }
</script>
```


## API


Scroll props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    size       | 选填，滚动的距离              |    Number         |     0         |    任意整数           |
|    direction  | 选填，滚动方式               |    String          |     y         |    x,y               |
|    is-momentum| 选填，是否支持惯性           |    Boolean          |     true     |    true,false        |
|    is-bounce  | 选填，超出边界是否还能拖动    |    Boolean          |     true     |    true,false        |
|    bounce-time | 选填，回弹时间              |    Number          |     350         |    任意整数        |
|    prevent-default| 选填，是否阻止默认滚动事件 |    Boolean         |     true     |    true,false        |
|    disabled    | 选填，是否禁用              |    Boolean         |     false    |    true,false        |
|    pull-refresh | 选填，是使用下拉刷新         |    Boolean         |     false    |    true,false        |
|    refresh-status | 选填，刷新状态         |    String         |     ready     | ready,move,loading       |
|    is-refresh | 选填，刷新状态         |    Boolean         |     false            |    true,false        |
    



## 右侧示例代码


### 默认loadding
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Scroll</Hometitle>
        <div class="wrapper-example wrapper-example-scroll">
            <div class="wrapper-area-content" id="parent">
                <Scroll>
                    <ul>
                        <li>Pretty row 1</li>
                        <li>Pretty row 2</li>
                        <li>Pretty row 3</li>
                        <li>Pretty row 4</li>
                        <li>Pretty row 5</li>
                        <li>Pretty row 6</li>
                        <li>Pretty row 7</li>
                        <li>Pretty row 8</li>
                        <li>Pretty row 9</li>
                        <li>Pretty row 10</li>
                        <li>Pretty row 11</li>
                        <li>Pretty row 12</li>
                        <li>Pretty row 13</li>
                        <li>Pretty row 14</li>
                        <li>Pretty row 15</li>
                        <li>Pretty row 16</li>
                        <li>Pretty row 17</li>
                        <li>Pretty row 18</li>
                        <li>Pretty row 19</li>
                        <li>Pretty row 20</li>
                        <li>Pretty row 21</li>
                        <li>Pretty row 22</li>
                        <li>Pretty row 23</li>
                        <li>Pretty row 24</li>
                        <li>Pretty row 25</li>
                        <li>Pretty row 26</li>
                        <li>Pretty row 27</li>
                        <li>Pretty row 28</li>
                        <li>Pretty row 29</li>
                        <li>Pretty row 30</li>
                        <li>Pretty row 31</li>
                        <li>Pretty row 32</li>
                        <li>Pretty row 33</li>
                        <li>Pretty row 34</li>
                        <li>Pretty row 35</li>
                        <li>Pretty row 36</li>
                        <li>Pretty row 37</li>
                        <li>Pretty row 38</li>
                        <li>Pretty row 39</li>
                        <li>Pretty row 40</li>
                        <li>Pretty row 41</li>
                        <li>Pretty row 42</li>
                        <li>Pretty row 43</li>
                        <li>Pretty row 44</li>
                        <li>Pretty row 45</li>
                        <li>Pretty row 46</li>
                        <li>Pretty row 47</li>
                        <li>Pretty row 48</li>
                        <li>Pretty row 49</li>
                        <li>Pretty row 50</li>
                    </ul>
                </Scroll>
            </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Scroll,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Scroll,
        Button
    }
}
</script>
<style>
    .wrapper-example-scroll{
        position: fixed;
        width: 100%;
        height: 100%;
        padding-top: 0.45rem;
        top: 0px;
        left: 0px;
        border-top: solid 1px #ccc;
        box-sizing: border-box;
    }
    .wrapper-example-scroll .wrapper-area-content{
        width: 100%;
        height: 100%;
        overflow: hidden;
    }
    .wrapper-example-scroll .wrapper-area-content li{
        height: 0.4rem;
        line-height: 0.4rem;
        border-bottom: solid 1px #ccc;
        padding-left: 0.1rem;
        color: #666;
    }
    .wrapper-example-scroll .wrapper-area-content li: last-child {
        border-bottom-width: 0px;
    }
    .wrapper-example-scroll .wrapper-area-content .wrapper-area{
        padding: 0px;
        margin: 0px;
    }
</style>

```


