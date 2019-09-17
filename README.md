# gulu 一个vue ui 的组件

作者：zhumengyua

##安装
使用本框架前，请在css中开启 border-box

```
*{box-sizing:border-box}
```
##使用
1.请加入css,自定义颜色等样式
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
2.引入组件并使用
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