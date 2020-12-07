### CSS技巧  
##### 左图右文  
``` html run
<div>
  <img src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1607351309959&di=dcd405a3a29c93b5ed7164a25f8aa49d&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201610%2F12%2F20161012233503_hdYLt.thumb.700_0.jpeg" style="width: 150px">
</div>
```
``` css
img{
  float: left
}
p{
  overflow: hidden
}
```