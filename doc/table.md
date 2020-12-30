# Table表格
基于[el-table](https://element.eleme.cn/#/zh-CN/component/table)
#### 行内编辑以及悬浮分页示例  

<img src="https://861621821.github.io/repository/img/xilan/行内编辑悬浮分页.gif" style="background: url('https://861621821.github.io/repository/img/图片加载中.png')">  

>支持行内编辑
#### 基础用法
``` html
<template>
  <xl-table
    :data="tableData"
    :fields="fields"
    :float-paging="true"
    :el="el"
    :distance="40"
    :editHandler="editHandler"
  >
    <template v-slot:handler="{row}">
      <i class="el-icon-delete" @click="doDelete(row)"></i>
    </template>
  </xl-table>
</template>
<script>
  export default {
    data(){
      return{
        el: null,
        tableData: [{
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }, {
          name: '王小虎',
          address: '上海市普陀区金沙江路 1517 弄'
        }],
        fields: [{
          field: 'name',
          label: '姓名'
        },{
          field: 'address',
          label: '地址',
          type: 'edit'
        },{
          field: 'handler',
          label: '操作',
          type: 'template'
        }]
      }
    },
    mounted(){
      this.el = document.querySelector('body') 
    },
    methods: {
      editHandler(){},
      doDelete(){}
    }
  }
</script>
```
#### 属性  
| 参数  | 说明    | 类型 |  默认值 |
| ---- |  ----  | ----  | ----  |
| data  | 默认给表格的数据,会被attributes里有data覆盖  | Array  | - |
| immediate  | 是否立即调用getDataHandler请求数据  | Boolean  | - |
| attributes  | 表格属性，同[Table Attributes](https://element.eleme.cn/#/zh-CN/component/table) | Object |  - |
| fields  | 对象形式的字段集合，详情请查看[fieldsItem](/doc/table?id=fieldsItem)  | Array | - |
| getDataHandler  | 查询数据的回调方法   | Function(params) | - |
| editHandler  | 行内编辑回调方法，参数为修改后的该行数据  | Function(row)  | - |  
| floatPaging  | 是否开启悬浮分页  | Boolean  | false |  
| el  | 产生滚动的元素，监听此元素判断何时显示悬浮分页  | Function(row)  | - | 
| distance  | 页面中除table外的元素占去的高度，比如页面头部等，会影响悬浮分页  | Number  | 0 | 
  
#### fieldsItem  
| 参数  | 说明   | 类型 |  默认值 |
| ---- |  ----  | ----  | ----  |
| field | 字段 | String | - |
| label | 表头 | String | field |
| type | 单元格类型,详情请查看[type](/doc/table?id=type)| String | 默认为普通格式 |
| sortable | 是否可排序 | Boolean | false |
| sortMethod | 排序函数，参照[sort()](https://www.w3school.com.cn/js/jsref_sort.asp) | Function(a,b)/String(函数体) | - |
| width | 列的宽度(需要带上px) | String | auto |
| filter | 列筛选 | Boolean | false |
| editType | 行内编辑模式（仅在type=edit有效，目前支持input/select） | String | input |
| editOptions | 行内编辑模下拉框的选项列表（仅在type=edit且editType=select有效） | Array | false |

#### type  
| 可选值 | 说明   |
| ---- |  ----  |
| template |  自定义插槽模式，__需要指定v-slot为当前字段名(如:v-slot:demandId，demandId为该列的field)__  |
| edit |  行内编辑模式  |

#### Methods 
| 方法 | 说明   |
| --- | --- |
| refreshData |  刷新表格数据  |

#### 属性示例 
###### fields
```js
fields: [{
  field: 'demandId',
  label: 'ID',
  type: 'template',
  width: '80px'
},{
  field: 'priority',
  label: '优先级',
  type: 'template',
  sortable: true,
  sortMethod: this.sortByPriority,
  width: '100px'
}]
```
###### editOptions
```js
editOptions: [{
  label: '在职',
  value: '1'
},{
  label: '离职',
  value: '0'
}]
```
