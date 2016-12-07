---
title: Alert 弹框
date: 2016-10-19 15:25:42
tags: https://greatboy.github.io/mvui-example/#!/alert?hidetitle=true
categories:
- View
---


# Alert 弹框


## 概述
Alert 是Modal的一个单例，支持remove方法销毁，同时也 show 方法的参数为对象,属性为 title（标题），content（内容），okText（按钮文本），onClose(关闭回调)


## 如何使用
Alert 组件代用api显示

``` javascript
// 引入
import { Alert } from 'mvui';
// 调用方法
Alert.show({
    title: '我是title',
    content: '我是内容',
    onClose: function(){
        Alert.remove();
    }
});
```


## API

Alert show param参数

|     属性       | 说明                       |        类型           |    默认值   |    可选值             |
| :------------- |:--------------------------| :----------------   | :------------|    :-----------------|
|    title      |       必填，标题             |    String          |      -       |     任意              |
|    content    |     必填，提示内容           |   String            |      -        |     任意              |
|    onClose    |        选填，关闭回调        |    Function         |      -       |       任意函数        |

Alert close 方法

Alert.close() 直接销毁alert


## 右侧示例代码


### 默认弹框
``` html
<template>
    <div class="wrapper-area">
        <div class="wrapper-area-title">默认alert弹框</div>
        <div class="wrapper-area-content">
            <div class="click-btn" @click="clickshow1">点击提示弹框</div>
        </div>
    </div>
</template>
<script>
    export default{   
        components: { 
            Alert
        },
        data(){
             return {
                show1: false,
             }
        },
        methods: {
            clickshow1(){
                Alert.show({
                    title: '我是title',
                    content: '我是内容'
                });
            },
        }
    }
</script>
```



### 弹框回调
``` html
<template>
    <div class="wrapper-area">
        <div class="wrapper-area-title">弹框回调</div>
        <div class="wrapper-area-content">
            <div class="click-btn" @click="clickshow2">点击提示弹框2</div>
        </div>
        <Tip :show.sync="showtip">{{tipmessage}}</Tip>
    </div>
</template>
<script>
    import { Tip, Alert } from 'mvui';
    export default{   
        components: { 
            Tip,
            Alert
        },
        data(){
             return {
                show2: false,
                tipmessage: '',
                showtip: false
             }
        },
        methods: {
            clickshow2(){
                var self = this;
                Alert.show({
                    title: '我是title',
                    content: '我是内容',
                    onClose: function(){
                        Alert.remove();
                        self.tipmessage = '弹框已经被销毁';
                        self.showtip = true;
                    }
                });
            },
        }
    }

</script>
```



