# 列表分页控件Pagination（PC）

---

##### 作用：分页显示；

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 说明：自定义控件对象名；
* ##### 显示跳转组件

  * 类型：（单选框）；

  * 说明：是否显示跳转页面的组件；默认不显示；

### 事件处理程序

* ##### PageIndexChanged

  * 调用时机：点击页码标签时；
  * 说明：展示点击的页面数据在此事件里面操作；

### 属性、方法

* ##### DataSource-属性，设置数据源；

  * 说明：对象，通过数据源赋值，告诉控件总数据条数和每页加载的数据量；
* * 示例：
  * ```js
    Pagination.DataSource={
    dataCount:2000,//总数据量
    perPageCount:30//每页加载数据量 };//Pagination为控件对象
    ```
* ##### currentPage-属性，获取当前点击页数；

  * 说明：数值，可以在PageIndexChanged事件中获取，从1开始。；
* * 示例：
  * ```js
    var currentPage = Pagination.currentPage;//Pagination为控件对象
    ```
* ##### perPageCount-属性，获取每页数据量；

  * 说明：数值，可以在PageIndexChanged事件中获取；
* * 示例：
  * ```js
    var perPageCount = Pagination.perPageCount;//Pagination为控件对象
    ```

* ##### SetPage\(page\)-方法，设置选中某一页；

  * 说明：参数page为需要选中的页数，数值；
* * 示例：
  * ```js
    Pagination.SetPage(3);//Pagination为控件对象
    ```

##### 



