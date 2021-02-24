# 证书申请 RequestCert

### 设计属性

* ##### 活动标题

  * 类型：字符串；

  * 值：默认值：证书申请；

  * 说明：
* ##### 活动注释

  * 类型：字符串；

  * 值：

  * 说明：对活动的说明；
* ##### 返回对象

  * 类型：字符串；

  * 默认值：secResp；

  * 说明：必填，格式参照“返回对象secResp格式”；
* ##### 证书DN

  * 类型：对象；

  * 说明：必填，格式：参照“证书DN格式”；
* ##### 证书密码

  * 类型：字符串；

  * 说明：必填，至少6位字符串；

#### 返回对象secResp格式：

```js
{
    "State":0,
    "Exception":"异常信息",
    "P10":
        {
            "containername":"证书容器名称",
            "p10":"证书标识"
        },
    "CertChain":
        {
            "status":0,
            "message":"成功",
            "data":"证书数据"
        }
}
```

#### 证书DN格式：

```js
{"DN":"CN=XXXX公司,OU=XXXX公司,O=SLHZ,L=市/州,ST=JL,C=CN",
    "column":
            {"column_ZCXQ":"单位名称：XXXX公司",
            "column_HU5Y":"所属机构：XXXX公司",
            "column_HMHW":"市/州",
            "column_XROM":"省",
            "column_P6FI":"统一社会信用代码",
            "column_JGSF":"项目编码，固定填写：SLHZ"},
    "extenset":
        {"ICRegNumber":"统一社会信用代码"}
    };
```



