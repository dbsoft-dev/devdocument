# 节点流 NodeFlow

---

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 说明：自定义控件对象名；
* ##### 节点流方向

  * 类型：（下拉选）；

  * 说明：设置节点排列方向；可选值：横向、纵向；

### 属性、方法

* ##### ItemSource-属性，设置数据源；

  * 说明：数组，Text:显示的文字；ImageUrl:显示的图片地址;Status：显示样式，default-灰色样式，默认值；highlight-高亮样式；
* * 示例：
  * ```js
    //NodeFlow为控件对象
    NodeFlow.ItemSource = [{"Text":"2020/1/18"
    , "ImageUrl":""
    , "Status":""},
    {"Text":"2020"
    ,"ImageUrl":"","Status":""
    }];
    ```

##### 



