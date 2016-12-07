---
title: Pullrefresh 下拉刷新
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/pullRefresh?hidetitle=true
categories:
- Other
---


# Pullrefresh 下拉刷新


## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
Pullrefresh 下拉刷新，支持三种情况，一种是默认window的滚动条、某元素的滚动条、以及scroll滚动条。


# 1）window默认滚动条 使用方法
需要将组件放到最外层里面的div就好,status既刷新状态，完成后，需要值为0，例如：


``` html
<template>
   <div>
       <Pullrefresh :status.sync="status" @on-refresh="refreshFunc"></Pullrefresh>
    <div>内容文章</div>
   </div>
</template>
<script>
import {
    Pullrefresh
} from 'mvui';
export default {
    components: {
        Pullrefresh
    },
    data() {
        return {
            status: 'ready'
        }
    },
    methods: {
        refreshFunc (e) {
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
            }, 1000);
        }
    }
}
</script>
```




# 2）某元素的默认滚动条 使用方法
需要将组件放到设置为滚动条元素的内部,.scroll-elem设置为overflow为auto或者scroll, status既刷新状态，完成后，需要值为0，例如：

``` html
<template>
   <div class="scroll-elem">
       <Pullrefresh :status.sync="status" @on-refresh="refreshFunc"></Pullrefresh>
        <div>内容文章</div>
   </div>
</template>
<script>
import {
    Pullrefresh
} from 'mvui';
export default {
    components: {
        Pullrefresh
    },
    data() {
        return {
            status: 'ready'
        }
    },
    methods: {
        refreshFunc (e) {
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
            }, 1000);
        }
    }
}
</script>
```



# 3）scroll滚动条 使用方法
需要设置scroll滚动条的三个属性，:pull-refresh="true" @on-refresh="pullRefresh" :refresh-status.sync="status"，
同时可以通过slot更改状态


``` html
<template>
   <div class="wrapper-area-content" id="parent">
        <Scroll :size.sync="size" :is-refresh.sync="isRefresh">
            <div slot="down">我是down按钮</div>
            <div slot="up">我是up按钮</div>
            <div slot="load">我是loadding</div>
            <ul>
                <li>文章内容</li>
            </ul>
        </Scroll>
    </div>
</template>
<script>
import {
    Pullrefresh
} from 'mvui';
export default {
    components: {
        Scroll,
        Pullrefresh,
    },
    data() {
        return {
            status: 'ready'
        }
    },
    methods: {
        pullRefresh (e) {
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
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
|    disabled   | 选填，是否禁用               |    Boolean          |      false  |  true , false            |
| prevent-default| 选填，是否阻止默认行为        |    Boolean          |       false |     true , false        |
|  scroll       | 选填，滚动条类型             |    String          |      window   |    window,scroll,other |
|direction      | 选填，滚动防线             |   String           |      y          |    x , y                |
|status         | 选填，状态             |    String       |   ready      |ready 准备,move下拉中,loading下拉完成|



## 右侧示例代码

### window 默认滚动条
``` html
<template>
    <div class="body-wrapper">
        <Pullrefresh :status.sync="status" @on-refresh="refreshFunc"></Pullrefresh>
        <Hometitle>PullRefreshWindow</Hometitle>
        <div class="wrapper-example wrapper-example-refresh-window">
            <div class="wrapper-area-content" id="parent">
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
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Pullrefresh,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Pullrefresh,
        Button
    },
    data() {
        return {
            status: 'ready'
        }
    },
    methods: {
        refreshFunc (e) {
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
            }, 1000);
        }
    }
}
</script>
<style>
header {
    position: relative;
    z-index: 100;
}
.wrapper-example-refresh-window .wrapper-area-content li {
    height: 0.4rem;
    line-height: 0.4rem;
    border-bottom: solid 1px #ccc;
    padding-left: 0.1rem;
    color: #666;
}

.wrapper-example-refresh-window .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-refresh-window .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>
```





### 某元素默认滚动条
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>PullRefreshElem</Hometitle>
        <div class="wrapper-example wrapper-example-refresh">
            <div class="wrapper-area-content" id="parent">
                <Pullrefresh :status.sync="status" @on-refresh="refreshFunc"></Pullrefresh>
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
            </div>
        </div>
</template>
<script>
import Hometitle from './common/hometitle.vue';
import {
    Panel,
    Pullrefresh,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Pullrefresh,
        Button
    },
    data() {
        return {
            status: 'ready'
        }
    },
    methods: {
        refreshFunc (e) {
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
            }, 1000);
        }
    }
}
</script>
<style>
header {
    position: relative;
    z-index: 100;
}
.wrapper-example-refresh {
    position: fixed;
    width: 100%;
    height: 100%;
    padding-top: 0.45rem;
    top: 0px;
    left: 0px;
    box-sizing: border-box;
}

.wrapper-example-refresh .wrapper-area-content {
    width: 100%;
    height: 100%;
    overflow: auto;
}

.wrapper-example-refresh .wrapper-area-content li {
    height: 0.4rem;
    line-height: 0.4rem;
    border-bottom: solid 1px #ccc;
    padding-left: 0.1rem;
    color: #666;
}

.wrapper-example-refresh .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-refresh .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>

```



### scroll 滚动条
``` html
<template>
    <div class="body-wrapper">
        <Hometitle>PullRefreshScroll</Hometitle>
        <div class="wrapper-example wrapper-example-refresh-scroll">
            <div class="wrapper-area-content" id="parent">
                <Scroll :pull-refresh="true" @on-refresh="pullRefresh" :refresh-status.sync="status">
                    <div slot="down">我是down按钮</div>
                    <div slot="up">我是up按钮</div>
                    <div slot="load">我是loadding</div>
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
    Pullrefresh,
    Button
} from 'mvui';
export default {
    components: {
        Hometitle,
        Scroll,
        Pullrefresh,
        Button
    },
    data() {
        return {
            status: 'ready'
        }
    },
    methods: {
        pullRefresh (e) {
            let self = this;
            setTimeout(function(){
                self.status = 'ready';
            }, 1000);
        }
    }
}
</script>
<style>
header {
    position: relative;
    z-index: 100;
}
.wrapper-example-refresh-scroll {
    position: fixed;
    width: 100%;
    height: 100%;
    padding-top: 0.45rem;
    top: 0px;
    left: 0px;
    box-sizing: border-box;
}

.wrapper-example-refresh-scroll .wrapper-area-content {
    width: 100%;
    height: 100%;
    overflow: hidden;
}

.wrapper-example-refresh-scroll .wrapper-area-content li {
    height: 0.4rem;
    line-height: 0.4rem;
    border-bottom: solid 1px #ccc;
    padding-left: 0.1rem;
    color: #666;
}

.wrapper-example-refresh-scroll .wrapper-area-content li: last-child {
    border-bottom-width: 0px;
}

.wrapper-example-refresh-scroll .wrapper-area-content .wrapper-area {
    padding: 0px;
    margin: 0px;
}
</style>

```