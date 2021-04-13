# 百度OCR OCR

作用：使用百度OCR功能，识别图片文字;

### 设计属性

* ##### 活动标题

  * 类型：字符串；

  * 值：默认值：文字识别；

  * 说明：
* ##### 活动注释

  * 类型：字符串；

  * 值：

  * 说明：对活动的说明；
* ##### 图片地址

  * 类型：字符串；

  * 说明：图片在服务器上的绝对地址；
* ##### 图片类型

  * 类型：字符串；

  * 示例：general\_basic；

  * 说明：需要识别的图片类型，为了提高识别（见下表）；

##### _图片类型说明：_

* **general\_basic——通用文字识别**

* **handwriting——手写文字识别**

* **idcard\_front——身份证-正面**

* **idcard\_back——身份证-反面**

* **bankcard——银行卡**

* **business\_license——营业执照**

* **passport——护照**

* **receipt——通用票据**

* **vat\_invoice——增值税发票**

* **train\_ticket——火车票**

* **driving**_**license——**_**驾驶证**

* **vehicle\_license——行驶证**

* **license\_plate——车牌**

* **vin\_code——VIN**

* **numbers——数字识别**

##### 回调函数参数：

* ##### ocrResult-获取识别结果

  * 类型：对象；

  * 说明：ocrResult在识别成功执行序列中可以获取到。获取的为字符串类型。如果为JSON格式字符串，可通过JSON.parse\(barcode\)转成JSON对象。



