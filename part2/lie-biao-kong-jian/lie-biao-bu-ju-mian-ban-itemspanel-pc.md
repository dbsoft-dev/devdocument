# 列表布局面板 ItemsPanel（PC）

---

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；
* ##### 显示标题

  * 类型：字符串；

  * 值：

  * 说明：设置显示标题；
* ##### 显示图标

  * 类型：（图片选择器）；

  * 值：

  * 说明：设置显示图片；
* ##### 停留时间\(ms\)

  * 类型：数值；

  * 值：默认值：8000

  * 说明：设置消息提醒停留时间，数值类型，单位毫秒\(ms\)，默认8000ms；
* ##### 消息类型

  * 类型：字符串；

  * 值：

  * 说明：用于处理消息的标记，监听某一类型的消息（平台消息推送中的消息Id），自定义；
* ##### AppId

  * 类型：字符串；

  * 值：

  * 说明：监听的消息的应用标识（监听哪个应用的消息）；
* ##### 全局消息

  * 类型：（单选框）；

  * 值：

  * 说明：设置是否监听全局消息；

### 事件处理程序

* ##### ListenerOnLoad

  * 调用时机：监听器加载时；
  * 说明：
* ##### ListenerOnMsg

  * 调用时机：监听到消息时；
  * 说明：在此事件里，通过thisControl. MsgObject获取到消息对象
* ##### ListenerUnLoad

  * 调用时机：监听器卸载时；
  * 说明：
* ##### Click

  * 调用时机：点击控件时
  * 说明：
* ##### TipBoxClick

  * 调用时机：点击弹出的消息显示框时；
  * 说明：触发对象为消息显示框对象，消息显示框对象的属性DataContext记录着接受到的消息体对象；

### 属性、方法

* ##### Badge-属性，设置右上角角标值；
* * 说明：数值；
* * 示例：
  * ```js
    //MessageListener为控件对象
    MessageListener.Badge =2;
    ```
* ##### ShowMessageList-方法，显示消息列表；
* * 说明：方法；
* * 示例：
  * ```js
    //MessageListener为控件对象
    MessageListener.ShowMessageList();
    ```
* ##### HideMessageList-方法，隐藏消息列表；
* * 说明：方法；
* * 示例：
  * ```js
    //MessageListener为控件对象
    MessageListener.HideMessageList();
    ```
* ##### ItemSource-属性，设置消息列表数据源；
* * 说明：数组；
* * 示例：
  * ```js
    //MessageListener为控件对象
    MessageListener.ItemSource =[{Title:"标题",Text:"内容"},{Title:"标题",Text:"内容"}];
    ```



