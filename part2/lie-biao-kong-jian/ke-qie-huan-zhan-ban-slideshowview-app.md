# 可切换展板SlideShowView（APP）

---

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 说明：自定义控件对象名；
* ##### 切换间隔

  * 类型：数值；

  * 值：默认值：5000；

  * 说明：单位：毫秒；
* ##### 切换效果

  * 类型：（下拉选框）；

  * 说明：可选值：左右滑动、上下滑动、淡入淡出；
* ##### 项目成员

  * 类型：字符串；

  * 说明：

### 属性、方法

* ##### ItemSource-属性，设置数据源；

  * 说明：数组;
* * 示例：
  * ```js
    //SlideShowView为控件对象
    //字段说明：
    //Mode：加载页面资源的显示模式，模式区别参考加载UI；
    //ResourceText：页面资源展示标题；
    //ResourceUri：展示的页面资源地址；
    //ImageUrl：展示的图片地址；
    SlideShowView.ItemSource = [{"Mode":0,"ResourceText":"广告","ResourceUri":"","ImageUrl":"图片地址"},
    {" Mode ":0,"ResourceText":"广告","ResourceUri":"","ImageUrl":""}];
    ```



