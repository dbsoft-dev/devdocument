# 视图（控件）公共属性设置

## 布局设置

* ##### 漂浮位置Float；

  * 属性设置：下拉框；

  * 可选值：未设置、靠左、靠右；

  * 说明：一行有极少的空间可供浮动控件，控件会跳至下一行，直到某一行拥有足够的空间为止。
* ##### 显示方式Display

  * 属性设置：下拉框；

  * 可选值：未设置、内联块、区块、弹性盒；

  * 说明：通过属性Visibled控制控件的显示与否，一定要为控件设置显示方式！
* ##### 定位方式Position

  * 属性设置：下拉框；

  * 可选值：未设置、相对布局、绝对布局、静态布局、固定布局；

  * 说明：子控件绝对布局，父容器相对布局；
* ##### 层叠顺序

  * 属性类型：数值；

  * 说明：可以有负值，仅对定位（绝对布局、固定布局）控件有效；如果为正数，则离用户更近，为负数则表示离用户更远。
* ##### 停靠方式

  * 属性设置：下拉框；

  * 可选值：未设置、靠上、靠左、靠右、靠下、填充、靠上；

  * 说明：只有控件被放置在“控件停靠面板”中，设置此属性才会有效果；
* ##### 圆角弧度

  * 属性类型：字符串

  * 值：数值+单位或者百分数；

  * 说明：设置控件四个角的圆角弧度值；
* ##### 透明度Opacity

  * 属性类型：数值；

  * 取值范围：0.0-1.0；

  * 说明：从 0.0 （完全透明）到 1.0（完全不透明）。
* ##### 左Left
* ##### 上Top
* ##### 右Right
* ##### 下Bottom
* ##### 高Height
* ##### 宽Width
* ##### 最大高宽Max
* ##### 最小高宽Min
* ##### 外边界设置Margin

  * 属性类型：字符串；

  * 值：5px-上、下、左、右；5px 10px-上下、左右;5px 10px 5px-上、左右、下;5px 10px 5px 20px-上、右、下、左;

  * 说明：可以有 1 到 4 个值，多个值用空格分隔；设置为百分比时，参照父容器的宽度的百分比值；
* ##### 内边界设置Padding

  * 同’外边界设置‘；
* ##### 水平对齐方式

  * 属性设置：下拉框；

  * 可选值：未设置、靠左对齐、居中对齐、靠右对齐、拉伸适应；

  * 说明：设置容器中子控件的水平位置；
* 纵向对齐方式

  * 属性设置：下拉框；

  * 可选值：未设置、顶部对齐、居中对齐、底部对齐、拉伸适应；

  * 说明：设置容器中子控件的水平位置；

## 颜色外观

##### 背景图片

* 选择图片按钮、清除图片按钮

* 通过点击相应按钮进入相应的界面设置背景BackgroundImageUrl；

* 1、设置背景图片：url\(“图片地址”\);

  2、设置渐变色：linear-gradient（）;

* 示例：

  ```js
  //设置背景图片或者背景渐变色
  1、url(“xxx.png”)；
  2、linear-gradient(120deg, #155799, #159957)；
  ```

* ##### 背景尺寸

  * 字符串,像素值、百分比、cover、contain
  * 示例：1、100px 100px;2、100% 100%；3、contain;
  * 说明：1、像素: 设置背景图像的宽度和高度，中间用空格分隔。如果只设置一个值，则第二个值会被设置为 “auto”。2、百分比:以父元素的百分比来设置背景图像的宽度和高度。3、cover：把背景图像扩展至足够大，以使背景图像完全覆盖背景区域。背景图像的某些部分也许无法显示在背景定位区域中。4、contain：把图像图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域。
* 背景颜色（颜色选择器）----设置控件背景显示颜色

* 前景颜色（颜色选择器）----设置控件内文字颜色

* 边框颜色（颜色选择器）----设置控件边框颜色

##### 边线宽度

* 字符串 数值+px

* 示例：2px设置控件边框线宽边线类型字符串

* 可选值：none\(无边框\)、hidden\(与none相同\)、dotted\(点状边框\)、dashed\(虚线\)、solid\(实线\)、double\(双线\)、inherit\(继承自父元素\)

示例：solid

* 说明：dotted和dashed在大多数浏览器中呈现为实线

* ##### 阴影

  * 一组按顺序填写的阴影描述词组，用空格分隔。

  * 语法\(注意顺序\)：h-shadow\(水平阴影的位置，必需\)v-shadow\(垂直阴影的位置，必需\)blur\(模糊距离，可选\)spread\(阴影尺寸，可选\)color\(阴影颜色，可选\)inset\(将外部阴影改为内部阴影\)

  * 示例：10px 10px 5px \#666

  * 说明：h-shadow和v-shadow必需，水平和垂直阴影的位置，允许负值；其余可选。每个阴影由 2-4 个长度值、可选的颜色值以及可选的 inset 关键词来规定。省略长度的值是 0。

## 字体设置

* ##### 字体

  * 下拉框
  * 可选值：未设置、宋体、楷体、黑体、仿宋
* ##### 选择风格

  * 下拉框
  * 可选值：未设置、正常、斜体、粗体
* ##### 字体大小

  * 字符串
  * 例：16px；
  * 说明：设置字体显示大小
* ##### 字体修饰

  * □下划线
  * □删除线



