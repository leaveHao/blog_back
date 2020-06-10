---
title: Angular学习笔记-02
abbrlink: '1e717450'
date: 2020-06-09 11:03:41
description: Angular创建组件
---

### 查看可创建的控件

```
ng g
```

### 创建自定义组件

```
ng g component 目录+组件名
例：ng g component components/home
```

### 使用组件

* #### 在home.component.html中填充内容
```
<h2>我是首页</h2>

```

* #### 在根组件中使用
```
<div>
  <app-home></app-home>
  <p>hello world!</p>
</div>

```
