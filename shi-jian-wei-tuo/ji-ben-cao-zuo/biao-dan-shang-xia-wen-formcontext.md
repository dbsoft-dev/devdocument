# 表单上下文 FormContext

作用：获取执行此事件的控件所在的表单（页面）上下文对象；

说明：属性包括“当前表单对象thisForm”和表单上设置了“数据属性”的控件的“数据属性”。

### 设计属性

* ##### 活动标题

  * 类型：字符串；

  * 值：默认值：formContext；

  * 说明：
* ##### 活动注释

  * 类型：字符串；

  * 说明：对活动的说明；
* ##### 对象变量

  * 类型：字符串；

  * 默认值:formContext；

  * 说明：对象变量名，存储值cmd.Sender.FormContext；

##### _备注：对于指定类型控件（文本输入框、多行文本框、密码输入框、日期选择控件PC、下拉列表框），设置了“数据属性”或者“数据域”名，就可以通过表单上下文对象取值。例如：文本输入框设置了“数据属性”名为name，就可以通过formContext.name获取这个文本输入框的值；多个指定类型控件设置了相同的“数据域”为data，则可以通过formContext.data获取这些控件的“数据属性—数据值”组成的对象。不同控件的数据属性不要设置相同名字。_



