# Converter 数据转换

#### 

* #### Converter.ToString\(string,format\)

  * ##### 作用：将字符转进行格式转换；
  * ##### 参数：string——字符串，需要转换的字符串；format——字符串，格式化字符串；
  * ##### 返回值：转换后的值；
  * ##### 说明： format值为空字符串或者undefined时，返回string，不做任何处理；
  * ##### 示例：

  ```js
  //format值：C，根据浏览器语言将数值格式化成货币，返回值为字符串；中文时返回￥5.00，英文时返回$5.00；
  var a = Converter.ToString('5','C');
  //format值：日期格式化yyyy-mm-dd hh:mm:ss，返回日期字符串；可选的格式化字符串："yyyy-MM-dd"、"HH:mm:ss"、"HH:mm"、
  //"yyyy-mm"、"yyyy-mm-dd hh:mm"、"yyyy-mm-dd hh:mm:ss"
  //示例：返回"2021-03-05"
  var b = Converter.ToString(new Date(),"yyyy-mm-dd");
  //返回值:"23.46"
  var c = Converter.ToString(23.4567,"0.00");
  ```
* #### Converter.Desensitization  \(str, rule\)

  * ##### 作用：个人信息脱敏处理；
  * ##### 参数：str-需要处理的信息字符串；rule-  处理规则:All-全部隐藏；Name-姓名；PhoneNumber-11位手机号码； IdentityCard-身份证号 18位； Address-住址信息；BankCard-银行卡号；Email-邮箱;Passport-护照9位，一位字母和八位数字组成，默认不隐藏；
  * ##### 返回值：脱敏处理后的字符串；
  * ##### 示例：
  * ```js
    //返回值133****1234
    Converter.Desensitization("13366661234", "PhoneNumber");
    ```



