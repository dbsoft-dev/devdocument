# 微信公众号打开应用页面

### 应用设置

#### 1、数据库中的应用信息添加字段：Params-对象类型

（测试库应用表路径：DB\_AzureBS/GLI\_Applications）

#### 2、Params格式：

![](/assets/params.png)

示例：

```js
{
    "AppId" : "e1334061f1954b10b25f1deee1c26725",
    "Co_id" : "",
    "Co_Name" : "深蓝应用开发练习",
    "Workspace" : {
        "ResourceUri" : "apps/e1334061f1954b10b25f1deee1c26725/ae36271a285345f59b1c31acee53c26e.scrn",
        "Text" : "深蓝应用开发练习"
    },
    "WxConfig" : {
        "WxAppId" : "wx724eb6e103686588",
        "SecretKey" : "c414de4feaab0e4a7b609c8f5a7088ce",
        "WPId" : "gh_7eac7b1133e0",
        "AccessToken" : "",
        "TokenTime" : ISODate("2018-03-19T06:26:05.847Z"),
        "JSTicket" : "",
        "JSTicketTime" : ISODate("2018-03-19T06:26:06.210Z"),
        "HomeUri" : "apps/e1334061f1954b10b25f1deee1c26725/ae36271a285345f59b1c31acee53c26e.scrn"
    }
}
```

### 3、拼接页面地址：

#### 拼接规则：

[https://open.weixin.qq.com/connect/oauth2/authorize?appid=](https://open.weixin.qq.com/connect/oauth2/authorize?appid=)微信公众号ID&redirect\_uri=回调地址&response\_type=code&scope=snsapi\_userinfo&state=应用AppID-页面资源路径.scrn-额外参数拼接\#wechat\_redirect

#### 额外参数拼接：

参数名=参数值，每对之间用’-’分隔；参数的获取：全局属性对象app.EnvironVariables.App\_Params.ExParams\(只有在微信公众号加载界面资源时才有值\)；所有拼接的参数对，会以键值对的形式存储在这个对象上；

##### 测试版示例：

https://open.weixin.qq.com/connect/oauth2/authorizeappid=wx724eb6e103686588&redirect\_uri=https://inkstone.dbazure.cn/defaultwx.aspx&response\_type=code&scope=snsapi\_userinfo&state=e1334061f1954b10b25f1deee1c26725-b17eb8220db64232a7fc7b8a3c268f28.scrn-name=jack-age=18\#wechat\_redirect

app.EnvironVariables.App\_Params.ExParams的值：{name: "jack",age: "18"}

##### 正式版示例：

https://open.weixin.qq.com/connect/oauth2/authorize?appid=wx724eb6e103686588&redirect\_uri=https://wechat.dbazure.cn/&response\_type=code&scope=snsapi\_userinfo&state=e1334061f1954b10b25f1deee1c26725-b17eb8220db64232a7fc7b8a3c268f28.scrn\#wechat\_redirect

##### 参数说明：

![](/assets/parameter02.png)



