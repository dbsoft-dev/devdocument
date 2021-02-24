## String-字符串对象

#### 学习文档：[https://www.w3school.com.cn/js/jsref\_obj\_string.asp](https://www.w3school.com.cn/js/jsref_obj_string.asp)

### 常用方法：

* #### charAt\(pos\)

  * #### 作用：获取指定位置的字符；
  * #### 说明：参数pos为数值类型，从0开始；
  * #### 示例代码：
  * ```js
    var char = “hello”.chartAt(3);
    //char为l;
    ```
* #### indexOf\(searchString\)

  * #### 作用：获取指定字符串第一次出现的位置;
  * #### 说明：参数为字符串；返回值为数值，从0开始。如果不存在指定的字符，返回-1；
  * #### 示例代码：
  * ```js
    var index = “hello”.indexOf(“el”);
    ```
* #### Split\(separator\)

  * #### 作用：用指定的字符分割字符串；
  * #### 说明：参数为字符串，返回分割后的字符数组；
  * #### 示例代码：

  ```js
   var arr = “hello,world,js”.split(“,”);
   //arr--->["hello","world","js"];
  ```



