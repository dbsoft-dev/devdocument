# Date 日期对象扩展方法

* #### addDays\(day\)

  * ##### 作用：添加天数；参数day为数值类型！可为负数；
  * ##### 示例：
  * ```js
    //返回日期为当前日期再加4天；
    new Date().addDays(4);
    ```
* #### addHours\(hour\)

  * ##### 作用：添加小时数；参数hour为数值类型！可为负数；
  * ##### 示例：
  * ```js
    //返回日期为当前日期再加24小时；
    new Date().addHours(24);
    ```
* #### addMinutes\(minutes\)

  * ##### 作用：添加分钟数；参数minutes为数值类型！可为负数；
  * ##### 示例：
  * ```js
    //返回日期为当前日期减去60分钟；
    new Date().addMinutes(-60);
    ```
* #### addSeconds\(seconds\)

  * ##### 作用：添加秒数；参数seconds为数值类型！可为负数；
  * ##### 示例：
  * ```js
    //返回日期为当前日期加上60秒钟；
    new Date().addSeconds(60);
    ```
* #### addYears\(year\)

  * ##### 作用：添加年数；参数year为数值类型！可为负数；
  * ##### 示例：
  * ```js
    //返回日期为当前日期加上1年；
    new Date().addYears(1);
    ```
* #### addMonth\(month\)

  * ##### 作用：添加月份数；参数month为数值类型！可为负数；
  * ##### 示例：
  * ```js
    //返回日期为当前日期加上12个月；
    new Date().addMonth(12);
    ```
* #### toLongTimeString\(\)

  * ##### 作用：获取时间字符串，返回值格式为'12:30:12'；
  * ##### 示例：
  * ```js
    //返回时间字符串；
    new Date().toLongTimeString();
    ```
* #### toLongDateString\(\)

  * ##### 作用：获取日期字符串，返回值格式为'2021-03-03'；
  * ##### 示例：
  * ```js
    //返回当前日期格式字符串
    new Date().toLongDateString();
    ```



