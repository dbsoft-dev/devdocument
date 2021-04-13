# 内容分享 WXShare（App）

作用：App中调起微信分享，将页面分享到微信好友或者微信朋友圈；

### 设计属性

* ##### 活动标题

  * 类型：字符串；

  * 值：默认值：微信分享；

  * 说明：
* ##### 活动注释

  * 类型：字符串；

  * 值：

  * 说明：对活动的说明；
* ##### 标题

  * 类型：字符串；

  * 示例：分享测试-title；

  * 说明：分享内容标题。不能为undefined！
* ##### 描述

  * 类型：字符串；

  * 示例：分享测试-subtitle；

  * 说明：分享内容描述。不能为undefined！
* ##### 缩略图

  * 类型：（按钮）；

  * 值：选择图片、清除图片；

  * 说明：分享内容展示缩略图，不能大于32k。不能为undefined！
* ##### 页面链接

  * 类型：字符串；

  * 值：1、砚台测试版：https://inkstone.dbazure.cn/sharepage.aspx?AppId=应用标识&PageUri=页面资源路径；

    2、砚台正式版：https://lc.dbazure.cn/sharepage.aspx?AppId=应用标识&PageUri=页面资源路径；

  * 说明：展示页面的URL地址；

##### 页面链接拼接说明：

1、示例：

https://inkstone.dbazure.cn/sharepage.aspx?AppId=e1334061f1954b10b25f1deee1c26725&PageUri=apps/e1334061f1954b10b25f1deee1c26725/75e7a05b4f3e4abb93b62e16a48bf313.scrn&\_id=123&name=Jack&age=18

2、AppId值为分享页面的应用标识，PageUri为分享页面的资源路径；

3、后面可以拼接需要传递的重要字段，字段之间用‘&’符号链接;

4、字段的键和值不能包含汉字！

5、在分享页面可以获取包含拼接键值对的传递对象；

6、获取传递对象方法\(固定\)：app.CurrentApp.EnvironVariables.QueryString



