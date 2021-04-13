# 汉堡菜单 HamMenu（PC）

---

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；
* ##### 项目成员

  * 类型：字符串；

  * 值：

  * 说明：设置绑定数据源字段；
* ##### 自动展开

  * 类型：（单选框）；

  * 值：默认：不展开

  * 说明：设置汉堡菜单选项是否自动展开；

### 事件处理程序

* ##### HamMenuItemClicked

  * 调用时机：用户点击Item时；
  * 说明：

### 属性、方法

* ##### Text-属性，获取/设置标题；

  * 说明：字符串类型；
* * 示例：
  * ```js
    HamMenu.Text = '标题';//HamMenu为控件对象
    ```
* ##### ItemSource-获取/设置数据源（项目成员）；

  * 说明：数组；
  * 结构说明：Text：显示标题；ImageUrl：图片地址；ResourceUri：页面资源地址;Mode:展现方式，设置为1；ResourceText：选项卡显示页面标题；Items：下级菜单的ItemSource值；
* * 示例：
  * ```js
    //HamMenu为控件对象
    HamMenu.ItemSource = [{"Text":"功能1","ImageUrl":"图片地址1","ResourceUri":"页面资源地址","Mode":1,"ResourceText":"页面资源地址",
      "Items":[{"Text":"功能11","ImageUrl":"图片地址11","ResourceUri":"页面资源地址"}]},
            {"Text":"功能2","ImageUrl":"图片地址2","ResourceUri":"页面资源地址"}];
    ```



