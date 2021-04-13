# 消息监听器 NotificationWatcher

---

作用：用于监听推送平台消息发出的消息推送，在监听到消息时做业务处理；

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；
* ##### 消息类型

  * 类型：字符串；

  * 值：

  * 说明：用于处理消息的标记，监听某一类型的消息（平台消息推送中的消息Id），自定义；
* ##### AppId

  * 类型：字符串；
  * 说明：应用标识；

### 事件处理程序

* ##### WatcherOnLoad

  * 调用时机：监听器加载后
  * 说明：
  * 备注：
* ##### WatcherOnMsg
* * 调用时机：监听到消息时；
  * 说明：在此事件里，通过thisControl. MsgObject获取到消息对象；
  * 备注：
* ##### WatcherUnLoad

  * 调用时机：监听器卸载时
  * 说明：
  * 备注：

### 属性、方法

* ##### MsgObject-属性，消息对象；
* * 说明：监听到的消息对象
* * 示例：
  * ```js
    var message = NotificationWatcher.MsgObject;//NotificationWatcher为控件对象
    ```

##### 



