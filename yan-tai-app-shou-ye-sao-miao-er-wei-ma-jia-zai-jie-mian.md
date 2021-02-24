# 砚台App首页扫描二维码加载界面

#### 1、二维码内容拼接格式：

示例：

```js
//说明：CodePrefix ---前缀，字符串，符合Javascript变量命名规范，名称唯一，不能重复；
//://---固定写法；
//{\"appid\":\"12131\",\"name\":\"ajfkhasdf\"}---需要传递的数据，JSON格式字符串；(引号需要转义！)
CodePrefix://{\"appid\":\"12131\",\"name\":\"ajfkhasdf\"}
```

#### 2、开发平台应用中创建‘UI流程’（公共方法），接收一个参数，参数值即为二维码中传递的数据，字符串类型；然后执行其他的操作，例如‘加载UI’；

#### 3、在MongoDB数据库DB\_Azure里表GLI\_AppCodeTypes中插入一条数据，表结构如下：

* _id_
  * _字符串_
  * _主键_

* _CodePrefix _
  * _字符串_
  * _示例：payPage_

* _AppId_
  * _字符串_
  * _应用\__id

* Callback
  * 字符串
  * 需要调用的公共方法名称
  * 示例：app.DynamicModules.Me7b092f17a994309a4615041dea2bea4

* Flag
  * 数值
  * 0

* Momo
  * 字符串
  * 备注信息;



