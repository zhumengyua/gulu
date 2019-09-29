# gulu 一个vue ui 的组件

作者：zhumengyua
[![Build Status](https://www.travis-ci.org/zhumengyua/gulu.svg?branch=master)](https://www.travis-ci.org/zhumengyua/gulu)


##介绍
这是我学习VUE的时候开发的组件
##开始使用
使用本框架前，请在css中开启 border-box
```
*{box-sizing:border-box}
*::before{box-sizing:border-box}
*::after{box-sizing:border-box}
```
请加入css,自定义颜色等样式
```
import 'gulu-text-2222/dist/index.css'
```
```
html {
     --button--height: 32px;
     --font-size: 14px;
     --button-bg: white;
     --button-active-bg: #eee;
     --button-radius: 4px;
     --color: #333;
     --border-color: #999;
     --border-color-hovet: #666;
        }
```
IE 15及以上支持此样式

2.安装gulu
```
npm i gulu-text-222
```

IE8及以上浏览器支持样式
3.引入组件并使用
```
import {Button,ButtonGroup,Icon} from 'gulu-text-2222'
```
export default {
  name: 'app',
  components: {
    'g-button':Button
  }}
```
  <g-button>欢迎使用</g-button>
```
4.引入svg symbols
 ```   <script src="//at.alicdn.com/t/font_1394984_wia9ihpt4d.js"></script>```

##参数详细说明
网格：
在g-col中: 
span:后面的数字表示占用了几份（总共24份）
offset:后面数字表示前面空几份
:ipad/:narrow-pc/：pc-/wide-pc:设置如果是这些设备的时候,应该怎么分
输入框：
disabled：禁止输入禁止点击（灰色）
readonly：禁止输入禁止点击（白色）
error="":红色警告框,后接提示文字
##联系方式
892244044@qq.com