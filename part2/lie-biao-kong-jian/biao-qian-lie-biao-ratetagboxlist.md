# 标签列表 RateTagBoxList

---

### 设计属性

#### （默认选项样式）：

* ##### 字体颜色

  * 类型：（颜色选择器）；

  * 说明：默认状态下字体颜色；
* ##### 边框颜色

  * 类型：（颜色选择器）；

  * 说明：默认状态下边框颜色；
* ##### 背景颜色

  * 类型：（颜色选择器）；

  * 说明：默认状态下背景颜色；

#### （选中时选项样式）：

* ##### 字体颜色

  * 类型：（颜色选择器）；

  * 说明：选中状态下字体颜色；
* ##### 边框颜色

  * 类型：（颜色选择器）；

  * 说明：选中状态下边框颜色；
* ##### 背景颜色

  * 类型：（颜色选择器）；

  * 说明：选中状态下背景颜色；
* ##### 选择模式

  * 类型：（下拉选）；

  * 说明：设置选择模式，可选值：单选、多选；
* ##### 未匹配到选项时动态添加

  * 类型：（单选框）；

  * 说明：赋值数据时，在未匹配到选项时，是否将未匹配到的选项作为可选项添加到列表；
* ##### 显示属性

  * 类型：字符串；

  * 说明：设置数据源中需要显示的文本字段名称，默认值Title；
* ##### 取值属性

  * 类型：字符串；

  * 说明：设置数据源中需要取值的属性，默认值Value；
* ##### 状态属性

  * 类型：字符串；

  * 说明：设置数据源中需要获取的状态属性，默认值Status；
* ##### 项目成员

  * 类型：字符串；

  * 说明：设置表单数据上下文对象中需要赋值给数据源的字段名；
* ##### 绑定路径

  * 类型：字符串；

  * 说明：设置表单数据上下文对象中需要赋值给选中值集合的字段名；

### 事件处理程序

* ##### ItemClick

  * 调用时机：标签被点击时；
  * 说明：事件的触发者\(cmd.Sender\)为Item
    Item对象的属性RateTagBoxList指向标签列表对象；DataContext属性记录Item的数据上下文对象；

### 属性、方法

* ##### ItemSource-属性，获取/设置数据源；

  * 说明：数组，默认值为undefined；设置可选项数据；字段说明：Title：显示文字，Status：选中状态，0-未选中，1-选中；Value:选项值；
* * 示例：
  * ```js
    RateTagBoxList.ItemSource = [{Title:"选项1",Value:0，Status:0},
    {Title:" 选项2",Value:2},
    {Title:" 选项1",Value:3},
    {Title:" 选项1",Value:4}]  ;//RateTagBoxList为控件对象
    ```
* ##### Datas-属性，赋值数据；

  * 说明：数组，给定的数据中，配匹到可选项的Title或者Value时，则显示选中状态；
* * 示例：
  * ```js
    //此时选项1为选中状态样式，其余选项为默认样式；
    RateTagBoxList.Datas = [{Title:"选项1",Value:0}];//RateTagBoxList为控件对象
    ```
* ##### SelectedItems-属性，所有选中的标签\(item\)数据上下文对象集合；

  * 说明：获取所有选中的数据对象集合，数组；未选中任何选项为空数组；
* * 示例：
  * ```js
    //结构——[{Title:" 选项1",Status:1},{Title:" 选项3",Status:1}]
    var selectedItems = RateTagBoxList.SelectedItems;   //RateTagBoxList为控件对象
    ```
* ##### Values-属性，获取/设置选中值集合；

  * 说明：数组；
* * 示例：
  * ```js
    RateTagBoxList.Values = ["选项1","选项2"];//RateTagBoxList为控件对象
    ```
* ##### SelectedTitles-属性，获取选中标题集合；

  * 说明：数组；
* * 示例：
  * ```js
    //结构——['选项1','选项2']
    var selectedValues = RateTagBoxList.SelectedTitles;   //RateTagBoxList为控件对象
    ```
* ##### SelectedValues-属性，获取选中值集合；

  * 说明：数组；
* * 示例：
  * ```js
    //结构——['1','2']
    var selectedValues = RateTagBoxList.SelectedValues;   //RateTagBoxList为控件对象
    ```



