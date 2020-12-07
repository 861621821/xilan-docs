# 省市区三级联动
基于[el-popover](https://element.eleme.cn/#/zh-CN/component/popover)
> 省市区三级联动组件，支持搜索，默认显示全国省市区信息，如需显示国外或国内部分省市区信息，可通过data字段传入
#### 示例

<img src="https://861621821.github.io/xilan-docs/static/img/xilan/省市区.gif" style="background: url('https://861621821.github.io/xilan-docs/static/img/图片加载中.png')">

#### 基础用法  
``` html
<template>
  <xl-cascader v-model="ssq"></xl-cascader>
</template>
<script>
  export default {
    data(){
      return{
        ssq: []
      }
    }
</script>
```
#### 自定义数据源
``` html
<template>
  <xl-cascader v-model="ssq" :data="ssqData"></xl-cascader>
</template>
<script>
  export default {
    data(){
      return{
        ssq: [],
        ssqData: [
          {
            name: '省份1',
            adcode: 'prov1',
            districtList: [
              {
                name: '城市1',
                adcode: 'city1-1',
                districtList: [
                  {
                    name: '区域1-1-1',
                    adcode: '111',
                  },
                  {
                    name: '区域1-1-2',
                    adcode: '112',
                  },
                  {
                    name: '区域1-1-3',
                    adcode: '113',
                  }
                ]
              },
              {
                name: '城市2',
                adcode: 'city1-2',
                districtList: [
                  {
                    name: '区域1-2-1',
                    adcode: '121',
                  },
                  {
                    name: '区域1-2-2',
                    adcode: '122',
                  },
                  {
                    name: '区域1-2-3',
                    adcode: '123',
                  }
                ]
              }
            ]
          }
        ]
      }
    }
</script>
```
#### 属性  
| 参数  | 说明    | 类型 |  默认值 |
| ---- |  ----  | ----  | ----  |
| data  | 自定义数据源，不传将默认展示国内所有地区信息  | Array  | - |

#### 方法  
| 方法名  | 说明    | 参数 |
| ---- |  ----  | ----  |
| reset  | 将联级置为默认状态  | -  |