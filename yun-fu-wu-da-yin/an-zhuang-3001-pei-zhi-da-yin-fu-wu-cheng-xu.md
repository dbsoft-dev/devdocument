# 安装、配置打印服务程序

#### 1、解压安装包PrinterDebug.rar

![](/assets/图片 1.png)

#### 2、修改解压后文件夹里的配置文件DBSoft.PrintingServer.exe.config

![](/assets/002.png)

**配置说明**：

```html
<!--公司关键字-->
<add key="co_id" value="0"/>
<!--商店关键字-->
<add key="de_id" value="0"/>
<!--机器编号-->
<add key="machine" value="DESKTOP-QK67J3P"/>
<!--mode - 0 JSON打印格式 1-HTML5打印格式-->
<add key="mode" value="1"/>
<!--数据库名称-->
<add key="dbname" value="DB_DataBase"/>
<!--存储过程名称-->
<add key="LoadingSP" value="EXEC SP_KM_TicketPrintService @Co_id,@De_id,@Machine,@ServerGuid"/>
<!--服务器地址-->
<add key="ServiceUrl" value="https://……………………"/>
<!--数据访问服务 MongoDB=DB.FX.Storage.MongoDBService SQL=DBSoft.AppService.DASqlService-->
<add key="svcuri" value="DBSoft.AppService.DASqlService"/>
<!-- 连接串 在指定服务器服务的Web.Config中加入或者查看-->
<add key="ConnectionString" value="DB_WMSystem"/>
```

#### 3、运行打印服务程序DBSoft.PrintingServer.exe；



