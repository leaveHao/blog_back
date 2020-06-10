---
title: Angular学习笔记-03
description: Angular声明属性、动态绑定数据、动态绑定属性、动态绑定类、数据双向绑定
abbrlink: 697644c6
date: 2020-06-09 17:30:48
---

### 声明属性的几种方式

* public 共有（默认） 可以在当前类里使用, 也可以在类外面使用
* protected 保护类型 只有在当前类和它的子类里使用

* private 私有 只有在当前类里可以使用

### 声明属性

* #### 规范写法

``` 
public message:any = 'hello world';
public userInfo:object = {
  userName : 'leaveHao',
  age : 22
};
```

* #### 简写

``` 
message = 'hello world';
userInfo:object = {
  name : 'leaveHao',
  age : 22
};
```

* #### 也可以只定义变量不赋值,在构造函数或方法中赋值

```
export class HomeComponent implements OnInit {
  public message:any;
  constructor() {
    this.message = '属性赋值';
   }
}
```

### 在模板中使用

```
<div>{{userInfo.age}}</div>
```

### 动态绑定属性

```
public imgURL:string = '图片地址'
```

```
<img [src]="imgURL"> //推荐
或者
<img src="{{imgURL}}">
```

### 在模板中绑定HTML(解析HTML标签)

```
public content:string = '<h2>这是一个h2标签,使用[innerHTML]来解析</h2>'
```

```
<span [innerHTML]="content"></span>
```

### 动态绑定类 ngClass

```
public flag:boolean = true;
```

```
.blue{
  color: lightblue;
}

.pink{
  color: lightpink;
}
```

```
<div [ngClass]="{'blue': flag ,'pink':!flag}">动态绑定类</div>
```

### 数据双向绑定

```
app.module.ts里引入表单模块
import { FormsModule } from '@angular/forms';
@NgModule({
  imports: [
    FormsModule
  ]
})
```

```
public name:string = 'hello'
```

```
<input type="text" [(ngModel)]="name">
```