---
title: vscode设置文件以何种方式高亮解析
date: 2020-12-24 09:43:58
tags:  vscode
categories: 工具使用
---



> 在实际工作中有时需要用到只定义文件后缀 ， 我最近遇到的项目需要定义.rule 文件 ，但语法类似javascript，文件编辑起来很费劲，因为不带高亮和语法提示，每次修改文件后缀也麻烦 ，我需要的是.rule 文件，以jjavascript的方式让vscode解析提示和高亮；

## 修改设置

首选项 -> 设置 ->文本编辑器 ->文件

![image-20201224095242258](https://raw.githubusercontent.com/zhangbowen-github/my-gallery/main/img/image-20201224095242258.png)

修改保存即可 ，语言要写全名 像`javascript `不要写成`js`

也可以直接编辑setting

## setting 修改

![image-20201224095505868](https://raw.githubusercontent.com/zhangbowen-github/my-gallery/main/img/image-20201224095505868.png)

json中添加

```json
  "files.associations": {
    "*.rule": "javascript"
  },
```

