---
title: Modal 模态框
date: 2016-10-19 15:25:42
tags: https://greatboy.github.io/mvui-example/#!/modal?hidetitle=true
categories:
- View
---


# Modal 弹出框

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
button 可以自定义通用属性class和style，以及show（是否显示），headerHide（隐藏header），footerHide（隐藏footerHide），cancelText（取消按钮文本），okText（确定按钮文本），width（width宽度）




## 如何使用


``` html
<Modal :show.sync="show">
    <div slot="header">Mvui 默认弹框</div>
    <div>这是一个弹窗</div>
</Modal>
<script>
    import { Modal } from 'mvui';
    export default{   
        components: { 
            Modal,
        },
        data(){
             return {
                show: true
             }
        },
    }
</script>
```


## API

Modal props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    show       | 必填，是否显示               |    Boolean          |              |       false,ture     |
|    header-hide | 选填，是否隐藏header        |    Boolean          |      false    | false,ture           |
|    footer-hide | 选填，是否隐藏footer        |    Boolean          |      false    |  false,ture          |
|    cancel-text | 选填，取消按钮文本           |    String          |      取消     |      任意文本      |
|    ok-text     | 选填，确定按钮文本           |    String          |      确定       |    任意文本        |
|    width      | 选填，弹框宽度               |   Number           |      80%      |    任意宽度         |
|    auto-close | 选填，点击的时候是否自动关闭   |   Boolean           |     true      |    默认开启         |





## 右侧示例代码


### 默认
``` html
<template>  
    <div class="body-wrapper">
        <Hometitle>Modal</Hometitle>
        <div class="wrapper-example">
            <div class="wrapper-area">
                <div class="wrapper-area-title">默认模态框</div>
                <div class="wrapper-area-content">
                    <div class="click-btn" @click="clickshow1">点击提示弹框</div>
                    <Modal :show.sync="show1">
                        <div slot="header">Mvui 默认弹框</div>
                        <div>这是一个弹窗</div>
                    </Modal>
                </div>
            </div>

            <div class="wrapper-area">
                <div class="wrapper-area-title">通过属性隐藏header 和 footer</div>
                <div class="wrapper-area-content">
                    <div class="click-btn" @click="clickshow2">点击提示弹框</div>
                    <Modal :show.sync="show2" :footer-hide="true" :header-hide="true">
                        <div slot="header">Mvui 默认弹框</div>
                        <div>
                            这是一个没有header和footer的弹框
                            <div @click="clickhide2">点我关闭</div>
                        </div>
                    </Modal>
                </div>
            </div>

            <div class="wrapper-area">
                <div class="wrapper-area-title">通过slot 隐藏header 和 footer</div>
                <div class="wrapper-area-content">
                    <div class="click-btn" @click="clickshow3">点击提示弹框</div>
                    <Modal :show.sync="show3">
                        <div slot="header"></div>
                        <div>
                            这是一个没有header和footer的弹框
                            <div @click="clickhide3">点我关闭</div>
                        </div>
                        <div slot="footer"></div>
                    </Modal>
                </div>
            </div>


            <div class="wrapper-area">
                <div class="wrapper-area-title">自定义header footer</div>
                <div class="wrapper-area-content">
                    <div class="click-btn" @click="clickshow4">点击提示弹框</div>
                    <Modal :show.sync="show4">
                        <div slot="header">
                            自定义模态框
                        </div>
                        <div>
                            <div>你好，我是自定义模块狂</div>
                            <div>你好，我是自定义模块狂框框</div>
                        </div>
                        <div slot="footer">
                            <div @click="clickhide4" style="padding-bottom: 10px;">自定义按钮</div>
                        </div>
                    </Modal>
                </div>
            </div>


            <div class="wrapper-area">
                <div class="wrapper-area-title">自定义header footer</div>
                <div class="wrapper-area-content">
                    <div class="click-btn" @click="clickshow5">事件回调</div>
                    <Modal :show.sync="show5" @on-cancel="oncancel" @on-ok="onok" :auto-close="false">
                        <div slot="header">
                            事件回调
                        </div>
                        <div>
                            <div>你好，我是自定义模块狂</div>
                            <div>你好，我是自定义模块狂框框</div>
                        </div>
                    </Modal>
                </div>
            </div>

            <Tip :show.sync="showtip">{{tipmessage}}</Tip>
        </div>
    </div>
</template>
<script>
    import Hometitle from './common/hometitle.vue';
    import { Modal, Tip } from 'mvui';
    export default{   
        components: { 
            Hometitle,
            Modal,
            Tip
        },
        data(){
             return {
                show1: false,
                show2: false,
                show3: false,
                show4: false,
                show5: false,
                showtip: false,
                tipmessage: ''
             }
        },
        methods: {
            clickshow1(){
                this.show1 = true;
            },
            clickshow2(){
                this.show2 = true;
            },
            clickhide2(){
                this.show2 = false;
            },
            clickshow3(){
                this.show3 = true;
            },
            clickhide3(){
                this.show3 = false;
            },
            clickshow4(){
                this.show4 = true;
            },
            clickhide4(){
                this.show4 = false;
            },
            clickshow5(){
                this.show5 = true;
            },
            oncancel(){
                this.show5 = false;
                this.tipmessage = "点击cancel按钮";
                this.showtip = true;
            },
            onok(){
                this.tipmessage = "点击ok按钮";
                this.showtip = true;
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

