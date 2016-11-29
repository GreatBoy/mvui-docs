---
title: Accordion 折叠面板
date: 2016-10-19 15:25:42
tags: http://localhost:8080/#!/accordion?hidetitle=true
categories:
- View
---


# Accordion 折叠面板

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Accordion 折叠面板，需要有 Panel共同完成
Accordion 支持 class 、style 、accordion等三个属性
Panel 支持 class 、 style 、 open 、 key等属性
            

## 如何使用

``` html
<template>
    <div>
        <Accordion>
            <Panel>
                <div slot="title">测试啦啦啦</div>
              她坦白了我们所虚伪的 她单纯了我们所复杂的
              五年以来…
              5年的等待，是个漫长也是耗损的过程。
              看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
              她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
              这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
              是我们唯一相信且期待杨乃文的理由。
            </Panel>
            <Panel>
                <div slot="title">测试啦啦啦</div>
                  她坦白了我们所虚伪的 她单纯了我们所复杂的
                  五年以来…
                  5年的等待，是个漫长也是耗损的过程。
                  看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                  她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                  这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                  是我们唯一相信且期待杨乃文的理由。
            </Panel>
        </Accordion>
    </div>
</template>
<script>
import { Accordion,Panel } from 'mvui';
export default {
    components: {
        Accordion,
        Panel
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

Accordion Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    accordion      | 选填，是否显示手风琴效果   |    Boolean          |       false |       任意           |


Accordion Slot

|     name 名称      | 说明                     
| :------------- |:-------------------------- 
|     Panel           |    需要panel




Panel Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    open      | 必填，是否展开               |    Boolean          |       false   | true | false           |
|    key       | 必填，key标示的值            |    String          |      -         |  任意                |


Panel Slot

|     name 名称      | 说明                     
| :------------- |:-------------------------- 
|     title           |    title
|     默认           |    内容





## 右侧示例代码


``` html
<template>
    <div class="body-wrapper">
        <Hometitle>Accordion</Hometitle>
        <div class="wrapper-example wrapper-example-accordion">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认</div>
                <div class="wrapper-area-content">
                    <Accordion>
                        <Panel>
                            <div slot="title">测试啦啦啦</div>
                          她坦白了我们所虚伪的 她单纯了我们所复杂的
                          五年以来…
                          5年的等待，是个漫长也是耗损的过程。
                          看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                          她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                          这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                          是我们唯一相信且期待杨乃文的理由。
                        </Panel>
                        <Panel>
                            <div slot="title">测试啦啦啦</div>
                              她坦白了我们所虚伪的 她单纯了我们所复杂的
                              五年以来…
                              5年的等待，是个漫长也是耗损的过程。
                              看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                              她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                              这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                              是我们唯一相信且期待杨乃文的理由。
                        </Panel>
                    </Accordion>
                </div>
            </div>
             <div class="wrapper-area">
                <div class="wrapper-area-title">accordion</div>
                <div class="wrapper-area-content">
                    <Accordion accordion>
                        <Panel>
                            <div slot="title">测试啦啦啦</div>
                          她坦白了我们所虚伪的 她单纯了我们所复杂的
                          五年以来…
                          5年的等待，是个漫长也是耗损的过程。
                          看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                          她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                          这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                          是我们唯一相信且期待杨乃文的理由。
                        </Panel>
                        <Panel>
                            <div slot="title">测试啦啦啦</div>
                              她坦白了我们所虚伪的 她单纯了我们所复杂的
                              五年以来…
                              5年的等待，是个漫长也是耗损的过程。
                              看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                              她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                              这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                              是我们唯一相信且期待杨乃文的理由。
                        </Panel>
                    </Accordion>
                </div>
            </div>
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认打开</div>
                <div class="wrapper-area-content">
                    <Accordion accordion>
                        <Panel :open="true">
                            <div slot="title">测试啦啦啦</div>
                          她坦白了我们所虚伪的 她单纯了我们所复杂的
                          五年以来…
                          5年的等待，是个漫长也是耗损的过程。
                          看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                          她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                          这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                          是我们唯一相信且期待杨乃文的理由。
                        </Panel>
                        <Panel>
                            <div slot="title">测试啦啦啦</div>
                              她坦白了我们所虚伪的 她单纯了我们所复杂的
                              五年以来…
                              5年的等待，是个漫长也是耗损的过程。
                              看尽乐坛芭比娃娃的甜美面具，「性格」这两个字，似乎快要消失！
                              她的声音，她的个性，象徵著无可取代的高傲、独特的姿态，
                              这样一股充满灵魂的音乐、沉寂而刚苏醒的真声音，
                              是我们唯一相信且期待杨乃文的理由。
                        </Panel>
                    </Accordion>
                </div>
            </div>
            
            
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Accordion,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Panel,
        Accordion,
        Button
    },
    data() {
        return {
            selected: true,
        }
    }
}
</script>
<style lang="less">
    .wrapper-example-accordion .wrapper-area-content,.wrapper-example-accordion .wrapper-area{
        background: transparent;
    }
</style>

```
