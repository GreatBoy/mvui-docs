---
title: Pullload 下拉加载
date: 2016-10-19 15:25:24
tags: http://localhost:8080/#!/pullLoad?hidetitle=true
categories:
- Other
---


# Pullload 下拉加载


## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Pullload 下拉加载，支持三种情况，一种是默认window的滚动条、某元素的滚动条、以及scroll滚动条。


# 1）window默认滚动条 使用方法
需要将组件放到最外层里面的div的底部，status默认为ready，准备就绪，end为结束


``` html
<template>
   <div class="wrapper-example wrapper-example-load-window">
        <div class="wrapper-area-content" id="parent">
            <ul>
                <li v-for="(key, value) in data">
                    {{ value.message }} {{ key }}
                </li>
            </ul>
            <Pullload scroll="window" :status.sync="status" @on-load="loaded"></Pullload>
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Pullload,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Pullload,
        Button
    },
    data() {
        return {
            status: 'ready',
            data: [
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'}
            ]
        }
    },
    methods: {
        loaded: function(){
            let self = this;
            setTimeout(function(){
                self.status = 'end';
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
            }, 1000);
        }
    }
}
</script>
```



# 2）某元素的默认滚动条 使用方法
用法跟window很像，需要放到滚动元素#parent内的底部

``` html
<template>
   <div class="wrapper-example wrapper-example-load-window">
        <div class="wrapper-area-content" id="parent">
            <ul>
                <li v-for="(key, value) in data">
                    {{ value.message }} {{ key }}
                </li>
            </ul>
            <Pullload scroll="window" :status.sync="status" @on-load="loaded"></Pullload>
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Pullload,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Pullload,
        Button
    },
    data() {
        return {
            status: 'ready',
            data: [
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'}
            ]
        }
    },
    methods: {
        loaded: function(){
            let self = this;
            setTimeout(function(){
                self.status = 'end';
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
            }, 1000);
        }
    }
}
</script>
```



# 3）scroll滚动条 使用方法
跟window类似，需要放到scroll底部

``` html
<template>
   <div class="wrapper-example wrapper-example-load-scroll">
        <div class="wrapper-area-content" id="parent">
            <Scroll :size.sync="size" :is-refresh.sync="isRefresh">
                <div slot="down">我是down按钮</div>
                <div slot="up">我是up按钮</div>
                <div slot="load">我是loadding</div>
                <ul>
                    <li v-for="(key, value) in data">
                        {{ value.message }} {{ key }}
                    </li>
                </ul>
                <Pullload scroll="scroll" :size.sync="size" :status.sync="status" @on-load="loaded"></Pullload>
            </Scroll>
        </div>
    </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Scroll,
    Pullload,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Scroll,
        Pullload,
        Button
    },
    data() {
        return {
            status: 'ready',
            size: 0,
            isRefresh: false,
            data: [
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'}
            ]
        }
    },
    methods: {
        loaded: function(){
            let self = this;
            setTimeout(function(){
                self.status = 'end';
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.isRefresh = true;
            }, 1000);
        }
    }
}
</script>
```



## API

Pullrefresh Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|  scroll       | 选填，滚动条类型             |    String          |      window   |    window,scroll,other |
|size           | 选填，滚动条的距离，scroll为scroll的时候起作用 | Number|      0       |    任意   |




## 右侧示例代码

### window 默认滚动条
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>PullLoadWindow</Hometitle>
        <div class="wrapper-example wrapper-example-load-window">
            <div class="wrapper-area-content" id="parent">
                <ul>
                    <li v-for="(key, value) in data">
                        {{ value.message }} {{ key }}
                    </li>
                </ul>
                <Pullload scroll="window" :status.sync="status" @on-load="loaded"></Pullload>
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Pullload,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Pullload,
        Button
    },
    data() {
        return {
            status: 'ready',
            data: [
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'}
            ]
        }
    },
    methods: {
        loaded: function(){
            let self = this;
            setTimeout(function(){
                self.status = 'end';
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
            }, 1000);
        }
    }
}
</script>
<style>

.wrapper-example-load-window .wrapper-area-content li {
    height: 0.4rem;
    line-height: 0.4rem;
    border-bottom: solid 1px #ccc;
    padding-left: 0.1rem;
    color: #666;
}

.wrapper-example-load-window .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-load-window .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>

```





### 某元素默认滚动条
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>PullLoadElem</Hometitle>
        <div class="wrapper-example wrapper-example-load-elem">
            <div class="wrapper-area-content" id="parent">
                    <ul>
                        <li v-for="(key, value) in data">
                            {{ value.message }} {{ key }}
                        </li>
                    </ul>
                    <Pullload scroll="other" :status.sync="status" @on-load="loaded"></Pullload>
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Scroll,
    Pullload,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Scroll,
        Pullload,
        Button
    },
    data() {
        return {
            status: 'ready',
            data: [
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'}
            ]
        }
    },
    methods: {
        loaded: function(){
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
            }, 1000);
        }
    }
}
</script>
<style>
.wrapper-example-load-elem {
    position: fixed;
    width: 100%;
    height: 100%;
    padding-top: 0.45rem;
    top: 0px;
    left: 0px;
    border-top: solid 1px #ccc;
    box-sizing: border-box;
}

.wrapper-example-load-elem .wrapper-area-content {
    width: 100%;
    height: 100%;
    overflow: auto;
}

.wrapper-example-load-elem .wrapper-area-content li {
    height: 0.4rem;
    line-height: 0.4rem;
    border-bottom: solid 1px #ccc;
    padding-left: 0.1rem;
    color: #666;
}

.wrapper-example-load-elem .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-load-elem .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>


```



### scroll 滚动条
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>PullLoadScroll</Hometitle>
        <div class="wrapper-example wrapper-example-load-scroll">
            <div class="wrapper-area-content" id="parent">
                <Scroll :size.sync="size" :is-refresh.sync="isRefresh">
                    <div slot="down">我是down按钮</div>
                    <div slot="up">我是up按钮</div>
                    <div slot="load">我是loadding</div>
                    <ul>
                        <li v-for="(key, value) in data">
                            {{ value.message }} {{ key }}
                        </li>
                    </ul>
                    <Pullload scroll="scroll" :size.sync="size" :status.sync="status" @on-load="loaded"></Pullload>
                </Scroll>
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Scroll,
    Pullload,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Scroll,
        Pullload,
        Button
    },
    data() {
        return {
            status: 'ready',
            size: 0,
            isRefresh: false,
            data: [
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'},
                {'message': '我是消息'}
            ]
        }
    },
    methods: {
        loaded: function(){
            let self = this;
            setTimeout(function(){
                self.status = 'end';
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                self.data.push({'message': '我是消息'});
                debugger;
                self.isRefresh = true;
            }, 1000);
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

