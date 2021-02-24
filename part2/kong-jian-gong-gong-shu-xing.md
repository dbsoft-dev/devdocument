# 控件公共属性

* #### Enabled--控件可用性设置,true-可用;false-不可用；

  * ##### 类型：布尔；
  * ##### 值：true/false；
  * ##### 示例代码：

  ```js
  control.Enabled=true;
  ```
* #### Visibled--控件可见性设置,true-可见;false-不可见;_需要设置控件的“显示方式”才有效_；

  * ##### 类型：布尔；
  * ##### 值：true/false；
  * ##### 示例代码：
  * ```js
    control. Visibled =true;
    ```
* #### ReadOnly--控件只读性设置,true-只读;false-可编写；

  * ##### 类型：布尔；
  * ##### 值：true/false；
  * ##### 示例代码：
  * ```js
    control. ReadOnly =true;
    ```
* #### BackgroundColor--背景色设置

  * ##### 类型：字符串；
  * ##### 值：十六进制颜色值、RGB颜色字符串、RGBA颜色字符串、特定颜色字符串；
  * ##### 示例代码：
  * ```js
    control. BackgroundColor="#ddd666";
    ```
* #### BackgroundImageUrl--背景图片设置

  * ##### 类型：字符串；
  * ##### 值：
  * ##### 示例代码：
  * ```js

    ```
* #### Color--前景色（字体）颜色设置

  * ##### 类型：字符串；
  * ##### 值：十六进制颜色值、RGB颜色字符串、RGBA颜色字符串、特定颜色字符串；
  * ##### 示例代码：
  * ```js
    control.Color = "#ddd666";
    ```
* #### Display--控件显示方式

  * ##### 类型：字符串；
  * ##### 值：“block”/ “inline-block”/ “none”；
  * ##### 示例代码：
  * ```js
    control.Display = "block";
    ```
* #### Width--控件宽度

  * #### 类型-字符串；
  * #### 值：数值+单位或者百分比；
  * #### 示例代码：
  * ```js
    control.Width = "100px";
    control.Width = "50%";
    ```
* #### Height--控件高度

  * ##### 值：数值+单位或者百分比；
  * ##### 示例代码：
  * ```js
    control.Height = "100px";
    control.Height = "50%";
    ```
* #### ComputedHeight--获取计算高度

  * ##### 类型-字符串，只读属性；
  * ##### 值：数值+"px";
  * ##### 说明：控件渲染到界面后才能获取到值；
* #### ComputedWidth--获取计算宽度

  * ##### 类型：字符串，只读属性；
  * ##### 值：数值+'px';
  * ##### 说明：控件渲染到界面后才能获取到值；

    #### 



