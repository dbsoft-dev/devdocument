# 转盘控件TurnPlate（APP）

---

##### 作用：多用于抽奖；

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 说明：自定义控件对象名；
* ##### 开始按钮图片

  * 类型：（图片选择器）；

  * 说明：设置中间开始按钮的图片；
* ##### 背景图片

  * 类型：（图片选择器）；

  * 说明：设置背景显示的图片；
* ##### 旋转时间

  * 类型：数值；

  * 值：示例：9000

  * 说明：设置旋转的时间，单位为毫秒；默认值8000；
* ##### 旋转圈数

  * 类型：数值；

  * 说明：设置转盘旋转的圈数，默认11；

### 事件处理程序

* ##### RotateStart

  * 调用时机：点击按钮开始旋转时；
  * 说明：
* ##### RotateStop

  * 调用时机：旋转停止时；
  * 说明：在此事件中可通过属性SelectedData获取指针指向的区域数据；

### 属性、方法

* ##### ItemSource-属性，设置数据源；

  * 说明：数组，text：显示文字；color：显示区块背景色；imgSrc：显示图片地址；fontColor：文字颜色；fontFamily：文字字体；fontStyle：文字字体样式；
* * 示例：
  * ```js
    //TurnPlate为控件对象
    TurnPlate.ItemSource = [{
        text:"9积分",
        color:"#FFF4D6",
        imgSrc:"1.png",
        fontColor:"#5b2aff",
        fontFamily:"Microsoft YaHei",
        fontStyle:"normal"
    },{
        text:"5元代金券",
        color:"#FF6F55",
        imgSrc:"2.png"
    },{
        text:"水壶",
        color:"#7AFF79",
        imgSrc:"1.png"
    },……];
    ```
* ##### SelectedIndex-属性，设置选中项；

  * 说明：数值，设置转盘停止后的选中项，取值从0开始，如不设置，默认选中随机值；
* * 示例：
  * ```js
    TurnPlate.SelectedIndex = 1;//TurnPlate为控件对象
    ```
* ##### CanRotate-属性，设置是否可以旋转；

  * 说明：布尔类型，设置转盘是否可以旋转；
* * 示例：
  * ```js
    TurnPlate.CanRotate = true;//TurnPlate为控件对象
    ```
* ##### SelectedData-属性，获取旋转停止后指向区域的数据；

  * 说明：对象；在RotateStop事件中可以获取到值；
* * 示例：
  * ```js
    var data = TurnPlate.SelectedData;//TurnPlate为控件对象
    ```

##### 



