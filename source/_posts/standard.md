---
title: 规范
date: 2016-10-19 15:23:55
tags:
categories:
- Summary
---



# 规范
## 使用规范 

使用者需要注意的规范。

## 组件 

使用:prop传递数据格式为 数字 或 布尔值 时，必须带:(兼容String除外，具体看组件文档)，比如：


正确的使用方法：
```
<Tip :show="true" ></Tip>
```

错误的使用方法：
```
<Tip show="true"></Tip>
```


有些组件需要使用.sync传递变量，主要原因在于当组件变化时候需要使父组件的样式也发生变化。


正确的使用方法：
```
<Tip :show.sync = "true" ></Tip>
```

错误的使用方法：
```
<Tip show.sync = "true"></Tip>
```


## 开发规范 

### 命名
    尽量简单、表意、风格统一。
### 目录
    组件在目录src/components/下，每个组件单独一个目录，目录命名使用小写
### 属性
    必须规定type或者使用validator进行验证
    如果validator验证为几个值中的一个，则使用src/utils/utils内的validate函数验证
### 事件 #
命名
    使用on-为前缀，比如on-change
规范
    使用$emit来对外触发事件
    嵌套组件之间通信，使用$parent和$children，而不用$emit，避免使用者错误使用自定义事件
### 其它 #
    css前缀使用mv-
贡献代码需要遵循的规范。