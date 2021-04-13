# 全局对象-app. CurrentApp

说明：在程序的任何地方都可以访问到app.CurrentApp这个全局的当前应用对象。

* ##### 属性：EnvironVariables

  * 类型：对象；
  * 说明：当前应用的环境变量对象；开发时可根据需求为此对象添加属性保存数据，方便在当前应用的其他界面获取；
* ##### 属性：AppId

  * 类型：字符串；
  * 说明：当前应用的标识；
* ##### 属性：startup

  * 类型：function；
  * 说明：当前应用的启动项；参数：1、cb-回调函数；2、mview-应用主页面表单对象；

### 启动项（函数）app.CurrentApp.startup中配置：

#### 1、配置当前应用的用户对象：app.CurrentApp.CurrentUser = {};

#### 2、配置当前用户对象的工作空间对象：app.CurrentApp.CurrentUser.WorkSpace = { ResourceUri :””, Text :””}ResourceUri：加载页面的资源地址；Text：加载页面的资源标题；

#### 3、配置安全控制台数据存储的数据库名app.EnvironVariables.SecurityDB=”数据库名”;

#### 4、配置安全控制台访问数据库的服务器地址：app.CurrentApp.EnvironVariables.ServiceUrl = “数据库所在服务器地址”；



