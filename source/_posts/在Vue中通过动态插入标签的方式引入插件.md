---
title: 在Vue中通过动态插入标签的方式引入插件
abbrlink: cca6d4c
date: 2020-11-15 10:58:31
description: 当我们需要在Vue中使用原生JS插件时,可以通过动态插入标签的方式引入插件。
cover: /images/vue_cover.png
tags:
	- 前端
	- Vue
categories: JavaScript
top_img: /images/default_cover.jpg
---
## 前言
当我们需要在Vue中使用原生JS插件时,可以通过下面的方式来使用该插件:
* 方法一：改造源码,使插件可以通过import的方式引入使用
* 方法二：通过动态插入标签的方式引入插件

## 动态插入标签
```JavaScript
  created(){
    const pinyin_dict_withtone = document.createElement('script');
    pinyin_dict_withtone.type = 'text/javascript';
    pinyin_dict_withtone.src = './static/dict/pinyin_dict_withtone.js';
    document.body.appendChild(pinyin_dict_withtone);
    pinyin_dict_withtone.onload = () => {
			//当文件加载完成时会触发onload事件,有些插件需要引入多个JS文件,那么则在下面继续引入依赖该文件的文件
      const pinyinUtil = document.createElement('script');
      pinyinUtil.type = 'text/javascript';
      pinyinUtil.src = './static/pinyinUtil.js';
      document.body.appendChild(pinyinUtil);
      pinyinUtil.onload = () => {
        //插件加载完成,你可以在这里或者后面的生命周期里调用插件里的方法
        console.log('插件加载完成')
      }
    }
  }
```