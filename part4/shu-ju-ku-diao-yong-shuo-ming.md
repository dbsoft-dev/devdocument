# 数据库调度使用说明

#### 1、MongoDB数据库调度

![](/assets/scheduler01.png)

1\).连接到数据库DB\_Scheduler

2\).打开数据表TM\_Tasks

3\).向表中添加一条数据，格式如下图：![](/assets/scheduler02.png)

##### 数据项说明：

\_id: ObjectId，唯一标识；

Title: 字符串，执行调度标题；

CmdLine: 字符串，执行的存储过程名；

TType: 字符串，调度类型；

StartTime: 字符串，开始时间；

EndTime: 字符串，结束时间；

CycleMode: 字符串，执行模式：0-间隔一定时间执行一次；3-在某个时间时间；

Interval: 数值，毫秒数，每间隔多少毫秒执行一次；

ExecuteAt: 字符串，在什么时间开始执行；

DBName: 字符串，存储过程所在的数据库名称；

SvrCntString: 字符串，数据库所在的服务地址；



#### 2、调度服务安装与配置

1\)、解压压缩包Scheduler.rar；

![](/assets/scheduler03.png)

解压后：![](/assets/scheduler04.png)

2\)、修改调度服务的配置文件DB.FX.SchedulerServer.exe.config，配置服务地址；如为本地服务器则不需更改；![](/assets/scheduler05.png)

3\)、执行安装程序InstallService.bat

