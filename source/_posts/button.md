---
title: Button 按钮
date: 2016-10-19 15:25:24
tags: https://greatboy.github.io/mvui-example/#!/button?hidetitle=true
categories:
- Basic
---


# Button 按钮

## 通用参数
###### 所有组件均支持class和style属性，class可以是vue变量也可以是字符串，style可以是字符串或者对象
###### 注：如果是变量需要在class前面加冒号,例如 :class="mv-button"


## 概述
button 可以自定义通用属性class和style，以及disabled（是否可用），type（按钮类型），shape（按钮形状），plain（是否无背景色），icon（icon种类），iconStyle（icon样式）


## 如何使用
使用Icon组件只需要指定图标的class即可，示例代码


``` html
<Button></Button>
```
渲染后为

``` html
<button class="mv-btn"></button>
```


## API

Button Props

|     属性       | 说明                       |        类型       |    默认值       |    可选值             |
| :------------- |:-------------------------- | :----------------  | :------------|    :-----------------|
|    class      | 选填，类名（可以设置icon）    |    String          |      -       |     任意              |
|    style      | 选填，内联样式,自由设置样式    |   [String,Object] |      -        |     任意              |
|    disabled   | 选填，系统功能是否可用        |    String          |              |       disabled        |
|    type       | 选填，系统功能按钮类型        |    String          |      -       | submit,button,reset   |
|    shape      | 选填，按钮形状，默认方形      |    String          |      -       |  round                |
|    plain      | 选填，是否无背景色           |    Boolean          |      false       |  true,false      |
|    icon       | 选填，图标类名               |    String          |      -       |    任意图标类名        |
|    iconStyle  | 选填，图标样式               |   [Object, String] |      -       |    任意               |



## 右侧示例代码


### 默认形状
``` html
<template>
    <Button>方形</Button>
</template>
<script>
    import { Button } from 'mvui';
    export default{   
        components: { 
            Button
        }
    }
</script>
```

### 形状控制
``` html
<template>
    <Button shape="round">圆形</Button>
    <Button shape="round" disabled="disabled">圆形</Button>
</template>
<script>
    import { Button } from 'mvui';
    export default{   
        components: { 
            Button
        }
    }
</script>
```


### 颜色
``` html
<template>
    <Button class="mv-btn-primary" type="submit">primary</Button>
    <Button class="mv-btn-success">success</Button>
    <Button class="mv-btn-warning">warning</Button>
    <Button class="mv-btn-danger">danger</Button>
    <Button class="mv-btn-royal">royal</Button>
</template>
<script>
    import { Button } from 'mvui';
    export default{   
        components: { 
            Button
        }
    }
</script>
```


### 是否有背景色
``` html
<template>
    <Button class="mv-btn-primary" type="submit">primary</Button>
    <Button class="mv-btn-primary" type="submit" :plain="true">primary</Button>
    <Button class="mv-btn-primary" type="submit" :plain="true" shape="round">primary</Button>
    <Button class="mv-btn-primary" type="submit" :plain="true" shape="round" disabled="disabled">primary</Button>
</template>
<script>
    import { Button } from 'mvui';
    export default{   
        components: { 
            Button
        }
    }
</script>
```



### 是否有icon以及修改icon样式
``` html
<template>
    <Button class="mv-btn-primary" icon="mv-icon-loading-1" icon-style="font-size: 0.14rem;">加载中...</Button>
    <Button class="mv-btn-primary" icon="mv-icon-loading-1" icon-style="color: red;font-size: 0.14rem;">加载完成</Button>
</template>
<script>
    import { Button } from 'mvui';
    export default{   
        components: { 
            Button
        }
    }
</script>

```


### 点击事件
``` html
<template>
    <Button @click="click">按钮点击</Button>
</template>
<script>
    import { Button } from 'mvui';
    export default{   
        components: { 
            Button
        },
        methods: {
            click(event){
                console.log(event);
                debugger;
            }
        }
    }
</script>

```




