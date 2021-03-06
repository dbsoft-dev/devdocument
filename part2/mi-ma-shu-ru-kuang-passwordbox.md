# 密码输入框 PasswordBox

---

##### 作用：用于输入比较隐秘的文本，不会直接显示输入的字符，会以圆点代替字符。

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；
* ##### 文本内容

  * 类型：字符串；

  * 说明：设置输入框默认显示字符串；
* ##### 数据域

  * 类型：字符串；

  * 值：

  * 说明：符合变量命名规则；数据域作为表单上下文的一个属性，所有指定数据属性的控件的值，都会保存在数据域对象中；
* ##### 数据属性

  * 类型：字符串；

  * 说明：符合变量命名规则；用于获取控件的值；控件的值会保存在表单上下文对象的数据属性上，如果指定了数据域，则会保存在数据域对象上；
* ##### 绑定路径

  * 类型：字符串；

  * 说明：为控件赋值的属性；页面加载时，会从表单的数据上下文对象DataContext中获取相应字段值进行显示；
* ##### 验证规则

  * 类型：（下拉选项）；

  * 说明：设置用户输入内容的验证规则；

  * 可选值:不能为空、必须为数值、必须为整数、必须为日期、身份证、移动电话号；
* ##### 输入提示

  * 类型：字符串；

  * 说明：设置输入框提示文字；
* ##### 错误提示

  * 类型：字符串；

  * 说明：设置用户输入错误后的提示信息；
* ##### 快捷键

  * 类型：字符；

  * 示例：y;

  * 说明：设置激活该输入框的快捷键,使用时使用alt+此快捷键组合使用；
* ##### Tab键序

  * 类型：数值；

  * 示例：5；

  * 说明：设置使用Tab键切换顺序，每个页面需设置不同的顺序级，如A页面为101、102…，那么B页面设置为201、202…；
* ##### 可用-设置控件是否可用；
* ##### 可见：设置控件是否显示；
* ##### 只读：设置文本输入框是否只读，不允许编辑；
* ##### 可用性表达式

  * 类型：字符串；

  * 示例：

  * ```js
    this.DataContext.Flag==2;//当控件对象的属性DataContext对象的Flag值为2时，控件可用，否则不可用；
    ```
  * 说明：界面加载时，通过控件的数据上下文某个属性值，控制控件是否可用；this指向当前控件对象；

### 事件处理程序

* ##### ValueChanged

  * 调用时机：文本输入框内值变化；
  * 说明：文本框失去焦点且文本框内值发生变化时，会执行此事件；
  * 备注：
* ##### Keypress

  * 调用时机：键盘按键按下；
  * 说明：如果想在点击回车时做处理，可以在此事件中判断event.keyCode == 13;
  * 备注：中文输入法时，只有直接按下数字键时有效。英文输入法时，对所有可输入字符按键有效。这个事件中获取文本框的值是键盘按下前的文本框值。
* ##### KeyDown

  * 调用时机：每次按键按下时；
  * 说明：
  * 备注：此事件中获取的Text为当前按键按下之前的文本框内容；
* ##### KeyUp

  * 调用时机：每次按键抬起时；
  * 说明：
  * 备注：此事件中获取的Text为当前按键按下之后的文本框内容；

### 属性、方法

* ##### Text-属性，获取/设置文本框值；

  * 说明：字符串类型；
* * 示例：
  * ```js
    PasswordBox.Text = '姓名'
    ```
* ##### TipText-获取/设置文本输入框提示文字；

  * 说明：字符串类型；
* * 示例：
  * ```js
    PasswordBox.TipText = '请输入您的账号'
    ```
* ##### focus-方法，激活（获取焦点）文本输入框；

  * 说明：
* * 示例：
  * ```js
    PasswordBox.TextBox.focus();    //PasswordBox为文本输入框控件对象
    ```
* ##### blur-方法，文本输入框失去焦点；

  * 说明：
* * 示例：
  * ```js
    PasswordBox.TextBox.blur();    //PasswordBox为文本输入框控件对象
    ```



