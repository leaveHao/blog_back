---
title: Angular学习笔记-04
abbrlink: f712d165
date: 2020-06-10 09:49:18
description: Angular数据循环、条件判断
---

### 普通循环 *ngFor

```
public arr:any[] = ['北京','上海','深圳'];
或者
public arr:Array<any> = ['北京','上海','深圳'];
```

```
<p *ngFor="let item of arr, let i = index">{{item}}{{i}}</p>
或者
<p *ngFor="let item of arr index as i">{{item}}{{i}}</p>
```

### 条件判断 *ngIf *ngSwitch

#### *ngIf

```
public flag:boolean = true;
```

```
<div>
  <img *ngIf="flag" src="assets/image/home_active.svg">
  <img *ngIf="!flag" src="assets/image/home.svg">
</div>
```

#### *ngSwitch

```
public status:number = 2;
```

```
<div [ngSwitch]="status">
  <div *ngSwitchCase="1">早上</div>
  <div *ngSwitchCase="2">中午</div>
  <div *ngSwitchCase="3">晚上</div>
  <div *ngSwitchDefault>其他</div>
</div>
```
