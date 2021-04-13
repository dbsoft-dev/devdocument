# 树形列表视图 TreeListView（PC）

---

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；
* ##### 项目成员

  * 类型：字符串；

  * 值：

  * 说明：
* ##### 显示属性

  * 类型：字符串；

  * 值：默认：Text；

  * 说明：数据源ItemSource中显示的字段名；
* ##### 取值属性

  * 类型：字符串；

  * 值：默认值：Text

  * 说明：数据源ItemSource中取值的字段名；
* ##### 图片属性

  * 类型：字符串；

  * 值：默认值：ImageUrl

  * 说明：数据源ItemSource中图片字段名；
* ##### 复选属性

  * 类型：字符串；

  * 值：

  * 说明：数据源ItemSource中复选属性字段名；
* ##### 自动展开节点

  * 类型：（单选框）；

  * 值：

  * 说明：是否自动展开节点；
* ##### 节点支持复选

  * 类型：（单选框）；

  * 值：

  * 说明：节点是否支持复选；
* ##### 节点支持拖拽

  * 类型：（单选框）；

  * 值：

  * 说明：节点 是否支持拖拽；

### 事件处理程序

* ##### TreeListNodeClick

  * 调用时机：单击节点；
  * 说明：
* ##### TreeListNodeDblClick

  * 调用时机：双击节点；
  * 说明：
* ##### TreeListNodeChecked

  * 调用时机：选择节点；
  * 说明：
* ##### TreeListViewSelectedNodeChanged

  * 调用时机：选择的节点改变
  * 说明：
* ##### TreeNodeDragDrop

  * 调用时机：拖拽节点时；
  * 说明：在此事件中，可以通过cmd.Sender获取一个对象：{ TreeView: 视图,SrcNode: 源节点,TargetNode: 目标节点,FormContext:视图的表单上下文 }，然后通过节点的属性DataContext获取节点的数据上下文对象；

### 属性、方法

* ##### ItemSource-属性，设置数据源；
* * 说明：数组；
  * 数据结构说明：Text：显示标题；Value:值；ImageUrl：图片地址；ResourceUri：页面资源地址;Mode:页面加载方式；ResourceText：选项卡显示页面标题；Items：下级菜单的ItemSource值；
* * 示例：
  * ```js
    //TreeListView为控件对象
    TreeListView.ItemSource =[{"Text":"功能1","Value":"值1","ImageUrl":"图片地址1","ResourceUri":"页面资源地址","Mode":1,"ResourceText":"页面资源地址",
        "Items":[{"Text":"功能11","Value":"值1","ImageUrl":"图片地址11","ResourceUri":"页面资源地址"}]},
        {"Text":"功能2","Value":"值2","ImageUrl":"图片地址2","ResourceUri":"页面资源地址"}];
    ```
* ##### SelectedNode-属性，获取/设置树形列表对象当前选中节点对象；
* * 说明：对象，获取/设置树形列表对象当前选中节点对象；
* * 示例：
  * ```js
    //TreeListView为控件对象
    var selectedNode = TreeListView.SelectedNode;
    ```
* ##### AddChildNode\(data\)方法，添加一级节点；
* * 说明：方法,为树形列表添加一级节点，参数data为添加节点的数据上下文对象；；
* * 示例：
  * ```js
    //TreeListView为控件对象
    TreeListView.AddNode(data);
    ```
* ##### CheckedNodes-属性，获取选中节点对象集；
* * 说明：数组，元素为选中节点对象；
* * 示例：
  * ```js
    //TreeListView为控件对象
    var checkedNodes = TreeListView.CheckedNodes;
    ```

#### 节点对象Node的属性/方法

* ##### TreeListView-属性，通过节点对象获取树形列表视图对象；
* * 说明：对象，通过节点对象获取树形列表视图对象；
* * 示例：
  * ```js
    //Node为节点对象
    var treeListView = Node.TreeListView;
    ```
* ##### ItemSource-属性，设置节点数据源；
* * 说明：数组，设置节点对象的数据源，数组中元素为子节点的数据对象；
* * 示例：
  * ```js
    //Node为节点对象
    Node.ItemSource = [{},{}];
    ```
* ##### Nodes-属性，子节点对象数组；
* * 说明：节点Node的子节点对象数组；
* * 示例：
  * ```js
    //Node为节点对象
    var nodes = Node.Nodes;
    ```
* ##### AddChildNode\(data\)-方法，为当前节点添加子节点；
* * 说明：参数data为新节点的数据上下文对象；
* * 示例：
  * ```js
    //Node为节点对象
    Node.AddChildNode(data)    ;
    ```
* ##### ParentNode-属性，获取当前节点的父节点；
* * 说明：对象，获取当前节点对象的父\(上一级\)节点；
* * 示例：
  * ```js
    //Node为节点对象
    var nodes = Node.ParentNode;
    ```
* ##### RemoveNode\(childNode\)-方法，移除节点的某个子节点；
* * 说明：参数childNode为Node的一级子节点；
* * 示例：
  * ```js
    //Node为节点对象
    Node.RemoveNode(childNode);
    ```
* ##### ClearNodes\( \)-方法，清空子节点；
* * 说明：方法,清空节点Node的一级子节点；
* * 示例：
  * ```js
    //Node为节点对象
    Node.ClearNodes();
    ```
* ##### Expand\( \)-方法，展开子节点；
* * 说明：展开显示节点的一级子节点；
* * 示例：
  * ```js
    //Node为节点对象
    Node.Expand();
    ```
* ##### Collapse\(\)-方法，折叠子节点；
* * 说明：折叠显示子节点；
* * 示例：
  * ```js
    //Node为节点对象
    Node.Collapse();
    ```
* ##### SetText\(text\)-方法，设置节点显示标题；
* * 说明：设置节点显示标题，参数text为字符串，表示显示的标题内容；
* * 示例：
  * ```js
    //Node为节点对象
    Node.SetText ('节点标题');
    ```
* ##### GetText\( \)-方法，获取节点显示标题；
* * 说明：获取节点显示标题，返回值为标题内容，字符串类型；
* * 示例：
  * ```js
    //Node为节点对象
    var text = node.GetText();
    ```

##### 



