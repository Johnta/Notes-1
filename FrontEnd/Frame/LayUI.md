`目录 start`
 
- [LayUI](#layui)
    - [使用](#使用)
        - [模块化](#模块化)
        - [非模块化](#非模块化)

`目录 end` |_2018-04-08_| [码云](https://gitee.com/kcp1104) | [CSDN](http://blog.csdn.net/kcp606) | [OSChina](https://my.oschina.net/kcp1104)
****************************************
# LayUI

## 使用

### 模块化
> 写法稍微复杂了些,但是提高了页面加载速度

引入核心文件:
```html
<link rel="stylesheet" href="../layui/css/layui.css"/>
<script src="../layui/layui.js"></script>
```
使用layer模块:
```js
layui.use(['layer'], function(){
    var layer = layui.layer;
    layer.msg('Hello World');
});
```


### 非模块化
