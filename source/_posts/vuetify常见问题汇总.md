---
title: vuetify常见问题汇总
date: 2021-06-09 10:06:39
tags:
	- Vuetify
	- Vue
categories: Vue
---

## vuetify 2.5.3版本提示DEPRECATION WARNING: Using / for division is deprecated and will be removed in Dart Sass 2.0.0.

github上的issues:https://github.com/vuetifyjs/vuetify/issues/13694

### 完整提示

```bash
DEPRECATION WARNING: Using / for division is deprecated and will be removed in Dart Sass 2.0.0.

Recommendation: math.div($grid-gutter, 6)

More info and automated migrator: https://sass-lang.com/d/slash-div

   ╷
62 │     'sm': $grid-gutter / 6,
   │           ^^^^^^^^^^^^^^^^
   ╵
    node_modules/vuetify/src/styles/settings/_variables.scss 62:11      @import
    node_modules/vuetify/src/styles/settings/_index.sass 1:9            @import
    node_modules/vuetify/src/styles/styles.sass 2:9                     @import
    node_modules/vuetify/src/components/VDataTable/_variables.scss 1:9  @import
    stdin 2:9                                                           root stylesheet

DEPRECATION WARNING: Using / for division is deprecated and will be removed in Dart Sass 2.0.0.

Recommendation: math.div($grid-gutter, 6)

More info and automated migrator: https://sass-lang.com/d/slash-div

```

### 解决

用  sass < 1.33 作为解决方法

官方的说明：我正在为此恢复修复，它完全破坏了注入自定义 sass 变量（[#13737](https://github.com/vuetifyjs/vuetify/issues/13737)）的项目。要使警告静音，请安装`sass@~1.32`

步骤：

修改package.json

```json
"sass": "~1.32",
```

然后 npm install

