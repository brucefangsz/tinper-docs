## 分页控件

分页控件提供了基础分页、无border分页、有间距的分页、多尺寸分页。

### 插件依赖

依赖于 <http://design.yyuap.com/static/uui/latest/js/u.js>

### 用法

1.分页通过添加`u-pagination`的样式来实现基本的分页效果

2.创建一个分页对象，方法：new u.pagination(paramter)

### js方法与参数
名称         | 方法参数                                                                    | 用法                                                                       | 描述        |
---------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------ | --------- |
pagination | 1.el:分页绑定的dom元素 2.jumppage：是否可跳转到某页。type为：boolean                       | new u.pagination(paramter)                                               | 创建一个分页对象  |
update     | 1.totalPages:总页数 2.pageSize:每页显示的条数 3.currentPage:当前页面 4.totalCount:总条数 | comp.update({totalPages: 100,pageSize:20,currentPage:1,totalCount:200}); | 更新分页的一些属性 |


### 基础分页

{% raw %}
<div id='pagination' class='u-pagination'>
</div>



<script>
  var element = document.getElementById("pagination");
  var comp = new u.pagination({ el: element,showState:false });
  comp.update({ totalPages: 100, pageSize: 20, currentPage: 1, totalCount: 200 });
  comp.on('pageChange', function(pageIndex) {
      console.log('新的页号为' + pageIndex);
  });
  comp.on('sizeChange', function(arg) {
      console.log('每页显示条数为' + arg[0]);
  });
</script>

{% endraw %}
``` html
<div id='pagination' class='u-pagination'>
</div>
```

``` js
  var element = document.getElementById("pagination");
  var comp = new u.pagination({ el: element,showState:false });
  comp.update({ totalPages: 100, pageSize: 20, currentPage: 1, totalCount: 200 });
  comp.on('pageChange', function(pageIndex) {
      console.log('新的页号为' + pageIndex);
  });
  comp.on('sizeChange', function(arg) {
      console.log('每页显示条数为' + arg[0]);
  });
```


### 有间距的分页
添加样式`pagination-gap`可以增加页码之间的间距

{% raw %}
<div id='paginationGap' class='u-pagination pagination-gap'>
</div>



<script>
 var paginationGap = document.getElementById('paginationGap');

 var comp = new u.pagination({ el: paginationGap, showState:false  });

 comp.update({ totalPages: 100, pageSize: 20, currentPage: 1, totalCount: 200 });

</script>

{% endraw %}
``` html
<div id='paginationGap' class='u-pagination pagination-gap'>
</div>
```

``` js
 var paginationGap = document.getElementById('paginationGap');

 var comp = new u.pagination({ el: paginationGap, showState:false  });

 comp.update({ totalPages: 100, pageSize: 20, currentPage: 1, totalCount: 200 });

```
