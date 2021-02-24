# PC系统安全控制台存储过程

#### 1、SP\_Sec\_AddUser2Group

```js
function (appid,co_id,u,ug)
{
    u=JSON.parse(u);
    ug=JSON.parse(ug);
    var u2g=db.Sec_User2Groups.findOne({UId:u._id,GId:ug._id});
    if(u2g==null)
    {
        u2g={_id:new ObjectId().str,AppId:appid,Co_id:co_id,UId:u._id,UserName:u.UserName,GId:ug._id,GroupName:ug.GroupName,GroupDesc:ug.GroupDesc};
        db.Sec_User2Groups.insert(u2g);    

    }
    return u2g;

}
```

#### 2、SP\_Sec\_AddUserGroup

```js
function (ugdata)
{
    var ugdoc=JSON.parse(ugdata);
    if(ugdoc._id!==undefined)
    {

        db.Sec_UserGroups.update({_id:ugdoc._id},{$set:{GroupName:ugdoc.GroupName,GroupDesc:ugdoc.GroupDesc}});

    }
    else
    {

        ugdoc._id=new ObjectId().str;

        db.Sec_UserGroups.insert(ugdoc);

    }
    ugdoc.ObjectTitle=ugdoc.GroupName;
    return ugdoc;

}
```

#### 3、SP\_Sec\_DelComponent

```js
function (cid)
{

    db.Sec_Components.deleteOne({_id:cid});
    db.Sec_Permissions.deleteMany({ResId:cid},false,true);
    return 0;

}
```

#### 4、SP\_Sec\_DelUserGroup

```js
function (ugid) {
    db.Sec\_UserGroups.deleteOne\({\_id:ugid}\);

    return 0;
}
```

#### 5、SP\_Sec\_GetU2OPermission

```js
function (uid,rid,spflag)
{
    //uid 用户标识
    //rid 对象标识
    //spflag //安全策略规则
    var pv=-1;


    pv=db.Sec_Permissions.findOne({ObjId:uid,ResId:rid});
    if(pv==null){

        //获取用户得安全组
        var ugs=db.Sec_User2Groups.find({UId:uid}).toArray();
        var pvs=db.Sec_Permissions.find({ObjId:{$in:ugs},ResId:rid}).sort({Priority:1}).limit(1).toArray();
        if(pvs.length==0)
            pv=-1;
        else
            pv=pvs[0].SecValue;
    }

    else
        pv=pv.SecValue;

    return pv;

}
```

#### 6、SP\_Sec\_LoadComs2Obj

```js
function (appid,pid,oid,flag,Co_id)
{
    var coms=new Array();
    if(flag==undefined)
        flag=0;
    var resitems=[];
    if(pid=="")
    {

            if(Co_id=="111")
            { 
                var Components_id="5a8121c6a5cf1b381cf3a079"
        var coms=db.Sec_Components.find({AppId:appid,PId:pid}).toArray();
        //var Components_id=
        } 
            else 
            {
        var Components_id="5a8121c6a5cf1b381cf3a079"
        var coms=db.Sec_Components.find({AppId:appid,PId:Components_id}).toArray();
         }
        //var coms=db.Sec_Components.find({AppId:appid,PId:pid}).toArray();
        resitems=coms;
                //resitems=[]

    }
    else
    {
        coms=db.Sec_Components.find({AppId:appid,PId:pid}).toArray();
        resitems=coms;
    }

    if(flag==1)
    {

        resitems.forEach(function(item)
        {

            item.SecValue=SP_Sec_GetU2OPermission(oid,item._id,0);
            if(item.SecValue!=-1)
                item.SecFlag=true;
            else
                item.SecFlag=false;

        });

    }

    return coms;

}
```

#### 7、SP\_Sec\_LoadConsole

```js
function (appid)
{
    var secPolicies={    StandaloneSignOn:false,
                        PwdComplex:false,
                        PwdDisableDate:false,
                        PwdVDays:0,
                        EnabledDeviceId:false,
                        EnabledIPAddress:false,
                        EnabledNFC:false};
    var secroot=[{Text:"系统安全控制台",ImageUrl:"themes/%currenttheme%/images/securityconsole/console.png",Items:[
    {Text:"用户信息",ImageUrl:"themes/%currenttheme%/images/securityconsole/user.png",PageResourceUri:"apps/3b5a0533153c4a0fa5f0a35305123423/952c8f17bb9343c9bb56eee32b4a7de8.scrn",NType:0},
    {Text:"用户组",ImageUrl:"themes/%currenttheme%/images/securityconsole/usergroup.png",PageResourceUri:"apps/3b5a0533153c4a0fa5f0a35305123423/81015f9fe97247a081283906592c171c.scrn",NType:0},
    {Text:"系统功能组件",ImageUrl:"themes/%currenttheme%/images/securityconsole/components.png",PageResourceUri:"apps/3b5a0533153c4a0fa5f0a35305123423/59f85d417e48630557f0b134.scrn",NType:2,_id:"",AppId:appid,PId:""}],
    PageResourceUri:"apps/3b5a0533153c4a0fa5f0a35305123423/d2601a8b76c543cd8c479f383eeaa348.scrn",
    Policies:secPolicies,NType:0
    }];

    return secroot;

}
```

#### 8、SP\_Sec\_LoadUser2Groups

```js
function (appid,co_id,uid) {
    var u2gs=db.Sec_User2Groups.find({AppId:appid,Co_id:co_id,UId:uid}).toArray();
    return u2gs;
}
```

#### 9、SP\_Sec\_LoadUserGroups

```js
function () {
    // write your code here
}
```

#### 10、SP\_Sec\_LoadUserPermissions

```js
function (uid,co_id)
{
    //用户权限列表
    var upvs=db.Sec_Permissions.find({ObjId:uid},{ResId:1,SecValue:1,Priority:1}).toArray();

    //用户组权限列表
    var ugs=db.Sec_User2Groups.find({UId:uid},{_id:0,GId:1}).toArray();

    var gids = [];

    ugs.forEach (function(item)
    {
        gids.push(item.GId);
    });


    var ugpvs=db.Sec_Permissions.find({ObjId:{$in:gids}},{ResId:1,SecValue:1,Priority:1}).sort({ResId:1,Priority:1}).toArray();

    var pvs={};
    upvs.forEach(function(pv)
    {
        var k="p"+pv.ResId.replace(/-/i,"");
        pvs[k]={SecVal:pv.SecValue,P:pv.Priority};

    });

    ugpvs.forEach(function(pv)
    {
        var k="p"+pv.ResId.replace(/-/i,"");
        var tpv=pvs[k];
        if(tpv!=undefined && tpv.Priority>pv.Priority)
                {}
        else
        {
            pvs[k]={SecVal:pv.SecValue,P:pv.Priority};

        }

    });

    return pvs;

}
```

#### 11、SP\_Sec\_LoadUsers

```js
function ()
{

    var users=db.Sec_AppUsers.find({}).toArray();
    return users

}
```

#### 12、SP\_Sec\_QueryGroups

```js
function (keyword,Co_id)
{

    var ugs=db.Sec_UserGroups.find({GroupName:{$regex:keyword, $options:'i'},Co_id:Co_id}).toArray();

    return ugs;

}
```

#### 13、SP\_Sec\_QueryUsers

```js
function (appid,co_id,keyword)
{
    var users=db.Sec_AppUsers.find({Co_id:co_id,UserName:{$regex:keyword, $options:'i'}}).toArray();
    return users;        
}
```

#### 14、SP\_Sec\_RemoveUser2Group

```js
function (id) 
{

    db.Sec_User2Groups.deleteOne({_id:id});
    return 0;

}
```

#### 15、SP\_Sec\_SaveComponent

```js
function(doc)
{
    var cdoc=JSON.parse(doc);

    if(cdoc._id==undefined)
    {
        cdoc._id=new ObjectId().str;
        db.Sec_Components.insert(cdoc);
    }
    else
    {

        db.Sec_Components.update({_id:cdoc._id},{$set:{AppId:cdoc.AppId,PId:cdoc.PId,Text:cdoc.Text,Description:cdoc.Description,ImageUrl:cdoc.ImageUrl,ResourceUri:cdoc.ResourceUri,Mode:cdoc.Mode,SecTag:cdoc.SecTag,Co_id:cdoc.Co_id}},false,true);

    }

    return cdoc;

}
```

#### 16、SP\_Sec\_SetPermission

```js
function(appid,co_id,objid,resid,priority,secval)
{
    var r=0;
    //删除权限定义
    if(secval==-1)
    {

        db.Sec_Permissions.deleteOne({ObjId:objid,ResId:resid});

    }
    else
    {

        var u=db.Sec_Permissions.update({ObjId:objid,ResId:resid},{$set:{SecValue:secval}},false,true);

        if(u.nMatched==0){
            var pdoc={ObjId:objid,ResId:resid,Priority:priority,SecValue:secval}
            pdoc._id=new ObjectId().str;
            db.Sec_Permissions.insert(pdoc);
        }

    }

    return r;

}
```



