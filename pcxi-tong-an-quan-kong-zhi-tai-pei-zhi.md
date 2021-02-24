# PC系统安全控制台配置

#### 1、应用启动项里配置应用所在服务器、数据库

app.CurrentApp.EnvironVariables.ServiceUrl = “应用配置的数据库所在服务器地址”

app.EnvironVariables.SecurityDB="应用存储数据的数据库名";

#### 2、复制存储过程到上面配置的数据库里（存储过程代码见文件[PC系统安全控制台存储过程](/pcxi-tong-an-quan-kong-zhi-tai-cun-chu-guo-cheng.md)）

#### 3、在执行加载系统安全控制台功能时调用方法DBFX.Security.LoadConsole\(\)

#### 4、界面就会被加载显示

![](/assets/security.png)

