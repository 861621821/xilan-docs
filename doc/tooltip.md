# Tooltip提示
基于[el-tooltip](https://element.eleme.cn/#/zh-CN/component/tooltip)
> 当文本过长显示不下时，打点显示，鼠标hover弹出完整文本，只在显示不下时出现
#### 示例  

<img src="https://861621821.github.io/xilan-docs/static/img/xilan/tooltip.gif" style="background: url('https://861621821.github.io/xilan-docs/static/img/图片加载中.png')">   

#### 用法  
``` html
<xl-tool-tip content="我是测试文本，显示不下的时候hover出现气泡提示"></xl-tool-tip>
```
#### 属性  
| 参数  | 说明    | 类型 |  默认值 |
| ---- |  ----  | ----  | ----  |
| content |  显示的内容  | String  | -  |
| placement |  Tooltip 的出现位置  | String  | top  |
| className |  自定义className  | String  | text-content  |