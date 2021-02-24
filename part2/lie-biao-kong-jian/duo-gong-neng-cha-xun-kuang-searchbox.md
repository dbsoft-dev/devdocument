# 多功能查询框 SearchBox

---

### ![](/assets/searchbox02.png)

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 说明：自定义控件对象名；
* ##### 按钮文字

  * 类型：字符串；

  * 示例：搜索;

  * 说明：设置按钮文字；
* ##### 显示图片

  * 类型：（按钮）；

  * 说明：设置显示图片；
* ##### 提示文字

  * 类型：字符串；

  * 值：默认为空

  * 说明：设置输入提示文字；
* ##### 搜索结果展示页面

  * 类型：字符串；

  * 值：示例：apps/e1334……

  * 说明：用于展示结果的页面资源地址；

### 事件处理程序

* ##### SearchingFor

  * 调用时机：点击按钮或者文本框激活时按下键盘“回车”键；
  * 说明：在这个事件里，拿到文本框值Text，进行数据库查询等操作；
* ##### ItemSelected

  * 调用时机：此事件需要手动调用方法OnItemSelected时才会触发；
  * 说明：在展示界面获取到点击数据后，手动调用OnItemSelected方法；

### 属性、方法

* ##### Text-属性，获取输入框文本；

  * 说明：字符串；
* * 示例：
  * ```js
    var text = SearchBox.Text;//SearchBox为控件对象
    ```
* ##### Show\(obj\)-方法，显示搜索结果页面；

  * 说明：此方法在SearchingFor事件里查询操作之后调用，参数为对象类型，里面包含查询到的数据，属性名自定义，在结果展示界面使用；
* * 示例：
  * ```js
    SearchBox.Show(obj);//SearchBox为控件对象
    ```
* ##### SearchBar-属性，在结果展示界面获取“查询面板”控件；

  * 说明：对象；
* * 示例：
  * ```js
    //在结果展示界面使用“当前表单”才能获取
    //thisForm为结果展示页表单对象
    var SearchBar = thisForm.SearchBar;
    ```
* ##### DataContext-属性，在结果展示界面获取搜索到的数据；

  * 说明：对象；
* * 示例：
  * ```js
    //获取到的对象就是调用Show(obj)方法传入的参数obj
    //thisForm为结果展示页表单对象
    var data = thisForm.DataContext;
    ```
* ##### OnItemSelected\(\)-方法，在结果展示界面触发ItemSelected事件；

  * 说明：选中结果中某行数据时调用此方法，把选中行数据赋值给“查询面板”控件的自定义属性，然后传回ItemSelected事件中；
* * 示例：
  * ```js
    //thisForm为结果展示页表单对象
    thisForm.SearchBar.OnItemSelected();
    ```

#### 使用过程示例：

![](/assets/searchbox01.png)



