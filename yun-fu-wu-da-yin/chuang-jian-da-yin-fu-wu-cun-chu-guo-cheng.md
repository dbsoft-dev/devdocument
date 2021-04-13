# 创建打印服务存储过程

> #### 注：存储过程名字配置到打印服务的配置文件中，打印服务启动后，打印服务自动调用；

打印服务调用打印存储过程时，**传递4个参数**，按顺序分别是：

```js
co_id：公司关键字
de_id：门店关键字
machine： 机器码
DeviceId： 设备号
```

在实际应用中，根据业务逻辑决定是否使用参数；

**示例：**

```js
SP_KM_TicketPrintService = function(co_id,de_id,machine,DeviceId){}
```



