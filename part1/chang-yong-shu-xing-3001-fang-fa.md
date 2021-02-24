# 平台常用属性/方法

* #### 判断横屏还是竖屏

  * 代码：

  ```js
  app.ScreenMode()；
  ```

  * 说明：返回值为0-纵向， 1-横向；
* #### App蓝牙打印

  * 代码：

  ```js
  //1、蓝牙打印机连接设置：
  Dbsoft.Printing.printSetup(cb)
  //2、打印内容：
  //1)、打印html内容：
  Dbsoft.Printing.printHtmlByBT(content,w,h);
  //2)、打印文本内容：
  Dbsoft.Printing.printDataByBT(text)
  ```

  * 说明：1、打印设置参数cb为回调函数，function\(\){};

    2、1\)、content为html字符串，w-页面宽度，例：”300”，h-页面高度，例:”300”；

    2\)、text-纯文本字符串，换行使用\n换行符；
* #### 打印PDF文档

  * 代码：

  ```js
  Dbsoft.Printer.PrintPDF(url,fName,dataJSON)
  ```

  * 说明：参数说明：url，字符串，PDF文档地址；fName：字符串，文档名称；dataJSON，JSON字符串，结构{"Printer":"打印机名称","Width":"宽度，单位为mm","Height":"高度，单位为mm ",“FromPage":"起始页码","ToPage":"结束页码","ScaleMode":"缩放比例，默认为0，按照纸张大小缩放；1-原PDF尺寸打印"}
* #### 砚台PC安装插件方法

  * 代码：

  ```js
  Dbsoft.System.LoadAssembly(assemblyName)
  ```

  * 说明：assemblyName:字符串，插件名字；\(首次安装插件后，需要重启应用\)；
* #### 下载文件方法

  * 代码：

  ```js
  //参数tasks类型为JSON字符串，格式：{"Tasks":[{"Url":"","FileName":""}]}
  Dbsoft.System.DownloadFiles(tasks);
  ```

  * 说明：Url：文件的绝对路径，FileName:保存文件时，为文件命名；
* #### 获取砚台运行的客户端操作系统

  * 代码：

  ```js
  app.OSType( )
  ```

  * 说明：返回值类型为字符串，“windows”-Windows系统；“android”-安卓系统；“ios”-iOS系统；
* #### 本地存储数据读取

  * 代码：

  ```js
  DBFX.Dbsoft.System.loadConfiguration(Name);
  ```

  * 说明：加载本地数据，Name字符串，数据字段名称，返回值：返回值 json字符串。备注：返回空字符串代表加载失败;
* #### 本地数据存储

  * 代码：

  ```js
  DBFX.Dbsoft.System.saveConfiguration(Name, JsonString);
  ```

  * 说明：保存本地数据；Name 字符串，数据字段名称，JsonString Json字符串，返回值：返回值 1-保存成功，0- 保存失败；
* #### 控件滚动到窗口的可视区域内

  * 代码：

  ```js
  Control.ScrollIntoView(mode);
  ```

  * 说明：Control为控件对象；mode为滚动参数，mode为Boolean类型时，1.如果为true，元素的顶端将和其所在滚动区的可视区域的顶端对齐。2.如果为false，元素的底端将和其所在滚动区的可视区域的底端对齐。mode为Object型参数时，结构：{behavior: "auto" \| "instant" \| "smooth",block: "start" \| "end"}；
* #### 获取设备码

  * 代码：

  ```js
  PC: app.EnvironVariables.MAC
  APP:app.EnvironVariables.DeviceId
  ```

  * 说明：
* #### 清缓存

  * 代码：

  ```js
  Dbsoft.System.clearWebCache()
  ```

  * 说明：清除砚台缓存;
* #### 判断当前运行环境（正式版or测试版）

  * 代码：

  ```js
  var host = window.location.host;
  ```

  * 说明：测试版：host == "inkstone.dbazure.cn"；
* #### 生成网页页地址的短链接服务

  * 代码：

  ```js
  服务地址：https://lc.dbazure.cn/svcbus/svcbus.ashx
  服务资源：DB.FX.Storage.MongoDBService
  存储服务：DBAzure
  数据库：DB_ShortUri
  存储过程：SP_GetShortUrl
  参数：长连接字符串
  ```

  * 说明：微信扫码加载界面时，拼接的地址过长，导致生成二维码复杂，不易扫描识别，所以使用短链接生成二维码；调用存储过程，参数传入长链接字符串，存储过程的返回值为生成的短链接；
* #### 视频会话

  * 代码：

  ```js
  //参数说明：
  //uid：字符串，""；
  //appid：字符串，AgoraRTC平台appid，"4df747ae375d4933ab9065506f63b08d"；
  //roomNum：字符串，视频会话房间号；
  //title：字符串，会话界面显示的标题，默认为roomNum；
  //iconImage:会话界面在对方未接通时显示图片地址；
  Dbsoft.System.Advance.makeVideoCall(uid,appid,roomNum,title,iconImage)；
  ```

  * 说明：
* #### 加载主题样式

  * 代码：

  ```js
  DBFX.Theme.LoadTheme(name,mode);
  ```

  * 说明：在启动项里调用此方法加载定制主题样式；name:字符串，主题名；mode:数值，0-App端，1-PC端；
* #### 阻止App页面触发左侧滑动事件回退页面

  * 代码：

  ```js
  thisForm.CanTouchBak=1；
  ```

  * 说明：页面布局了支持左右滑动的控件时，手指从左向右滑动时会触发回退页面的操作，可设置页面表单对象的CanTouchBak为1，阻止回退操作发生；
* #### 查看、浏览图片

  * 代码：

  ```js
  DBFX.Web.Controls.Image.ShowByFullScreen (imgurl)；
  ```

  * 说明：imgurl-字符串类型，图片地址；
* #### 设置App界面横屏显示

  * 代码：

  ```js
  Dbsoft.System.Advance.setScreenOrientation(mode)
  ```

  * 说明：参数mode为字符串类型，“0”-竖屏显示；“1”-横屏显示；默认竖屏显示；
* #### 拨打电话

  * 代码：

  ```js
  DBFX.Dbsoft.System.call(phoneNum);
  ```

  * 说明：phoneNum字符串类型，电话号码;
* #### 隐藏PC页面头部标题栏

  * 代码：

  ```js
  Form.HasTitleBar= false；
  ```

  * 说明：Form指代当前界面的表单对象；
* #### 隐藏APP页面头部导航栏

  * 代码：

  ```js
  Form.IsHideHeader = true;
  ```

  * 说明：Form指代当前界面的表单对象；
* #### 文字转语音

  * 代码：

  ```js
  Dbsoft.System.TextToSpeech(message, 1);
  ```

  * 说明：message:播放的语音字符串；
* #### 阻止事件冒泡

  * 代码：

  ```js
  window.event.cancelBubble = true
  ```

  * 说明：实际应用：ListView模板中的按钮控件点击事件执行时不触发ItemClick事件，在按钮点击事件里加上这段代码。
* #### 验证规则是否通过

  * 代码：

  ```js
  Validate( )
  ```

  * 说明：返回值为true时，说明验证通过，返回值为false是，说明验证未通过；可以通过thisForm对象调用，验证表单上所有设置了验证规则的控件是否通过验证；可以通过Panel对象调用，验证Panel内所有设置了验证规则的子控件是否通过验证；可以通过控件对象调用，验证控件的验证规则是否通过；未设置验证规则的控件，默认返回true。
* #### 加载动画显示与关闭方法

  * 代码：

  ```js
  //1、加载动画显示：
  DBFX.Web.Controls.LoadingPanel.Show(message);
  //2、加载动画关闭：
  DBFX.Web.Controls.LoadingPanel.Close()    ;
  ```

  * 说明：参数message为提示信息；
* #### 加载网页资源

  * 代码：

  ```js
  操作步骤：
  1、创建新的页面资源，布局一个“富文本显示框”控件，并为“富文本显示框”控件命名；
  2、在需要执行加载网页资源的事件委托里，执行“加载表单”，“加载表单”设置“UI资源”项为步骤1创建的页面资源地址；
  3、在步骤2的“加载表单”的“调用成功”里面进行“变量赋值”操作：
  uiview.FormControls.自定义富文本显示框名.Value = “<iframe width=\”100%\" frameborder=\”0\" height=\”100%\" src='http://www.dbsoft.com.cn'></iframe>”
  ```

  * 说明：width:显示网页资源的宽度；height：显示网页资源的高度；src:显示的网页资源地址；
* #### PC打印调用

  * 代码：

  ```js
  //调用步骤：
  //1、获取文档对象：
  var pdoc =Dbsoft.Printer.CreatePrintDocument(“”)；
  //2、文档对象写入HTML资源：
  pdoc.WriteHtmlData(htmlData);
  //3、展示打印预览界面：
  pdoc.ShowDialog()
  //或者直接打印
  pdoc.Print()    参数htmlData说明：
  //HTML页面标签样式转换成字符串；
  //示例：
  ”<div style=’width: 100%; top: 110px;’><a href='#marker' >跳转1</a><a href='testB.html#marker' >跳转2</a><a href='123.png' >跳转3</a></div>”
  ```

  * 说明：清除砚台缓存;
* #### PC图片预览+上传

  * 代码：

  ```js
  var imageJson = DBFX.Dbsoft.System.UploadImages(imageJSON)
  //参数imageJSON格式：
  {“Title”:””,
  “Action”:””,
  “ImageTypes”:[{“Text”:”图片名称，不允许重名”,”ImageUrl”:”图片地址”,”Width”:”图片宽度”,”Height”:”图片高度”}]}
  ```

  * 说明：参数说明：imageJson类型--json字符串,Title：上传图片的界面标题；Action：上传地址；ImageTypes：预览图片集合；返回值imageJson和参数imageJSON格式一致；
* #### 发送短信

  * 代码：

  ```js
  DBFX.ExInterfaces.SMS.SendMsg(phone,msg,button,func);
  ```

  * 说明：参数说明：
    phone:字符串，接收信息的电话号码；msg：字符串，普通的短信直接为信息内容字符串，发送验证码时信息格式为：”提示信息:{0}”；示例：”欢迎注册……您的注册验证码:{0}”；button:对象，触发发送验证码的按钮对象；func:回调函数，参数为发送的验证码，示例：function\(vcode\){button.SendCode=vcode;}；发送普通短信时， button参数传undefined；
* #### 数据二层分组

  * 代码：

  ```js
  var grpdata=DBFX.Data.Grouping(itemSource,[“分组列1”，”分组列2”],”分组集合属性名”)；
  ```

  * 示例：

  ```js
  var  students=[{Name:”张三”,Sex:”男”,Class:”a”},{Name:”张三”,Sex:”男”,Class:”a”},{Name:”张三”,Sex:”男”,Class:”a”},{Name:”白素贞”,Sex:”女”,Class:”a”},{Name:”小青”,Sex:”女”,Class:”B”},{Name:”许仙”,Sex:”男”,Class:”B”}]；
  var gstudents=DBFX.Data.Grouping(students,[“Sex”],”Students”); //按性别分组，返回对象
  [{Sex:”男”,Students:[{….}]},{Sex:”女”,Students:[{….}]}]
  ```
* #### PC图片浏览下载打印

  * 代码：

  ```js
  DBFX.Dbsoft.System.ShowPictures( imagejson);
  //imagejson格式:
  {
    “Title”:”xxx资质图片”,
    “ImageFolder”:”xxx资质图片”,
  “Images”:[{“Text”:””,”ImageUrl”:””,”Width”:”100”,”Height”:”333”}]}
  ```

  * 说明：参数说明：imagejson——json字符串  
    Title—标题；

    ImageFolder—下载时保存的文件夹名；

    Text—当前图片名（所有图片名不要重名，否则下载时会被覆盖）；

    ImageUrl—图片的URL地址；

    Width—图片显示宽度；

    Height—图片显示高度；
* #### App选择照片上传

  * 代码：

  ```js
  //callback：回调函数；
  //UploadUrl：上传地址，” https://wfs.dbazure.cn/wfs.ashx?AppId="+app.EnvironVariables.CurrentApp_AppId+"&UId=&OwnerId=”；
  //MsgBody：消息体；
  DBFX.Dbsoft.System.Advance.PickerImage.start(callback,UploadUrl,MsgBody);

  //回调函数参数为上传成功后的回调，可以进行分析、处理；
  //示例：
  function (dataObj) {       
  var ImgUrl = eval(“(“ + dataObj + “)”); 
    cmd.Sender.FormContext.Form.FormControls[“PhotoUrl”].ImageUrl = eval(ImgUrl.serverResponseMessage)[0].Url;
  }
  ```

  * 说明：
* #### App拍照上传

  * 代码：

  ```js
  DBFX.Dbsoft.System.Advance.CameraAdvance.start(callback,UploadUrl,MsgBody)
  //callback：回调函数；
  //UploadUrl：上传地址，” https://wfs.dbazure.cn/wfs.ashx?AppId="+app.EnvironVariables.CurrentApp_AppId+"&UId=&OwnerId=”；
  //MsgBody：消息体；    回调函数参数为上传成功后的回调，可以进行分析、处理；
  //回调函数示例：
  function (dataObj) {       
  var ImgUrl = eval(“(“ + dataObj + “)”); 
  cmd.Sender.FormContext.Form.FormControls[“PhotoUrl”].ImageUrl = eval(ImgUrl.serverResponseMessage)[0].Url;
  }
  ```

  * 说明：
* #### 关闭窗口

  * 代码：

  ```js
  @thisForm.Close()
  ```

  * 说明：
* #### 下载应用

  * 代码：

  ```js
  window.location.href    
  @”http://lc.dbazure.cn/app”（PC）版
  @”http://lc.dbazure.cn/Apps/9525c3d20cbd43b887029ce1d174c1be/download.html”（APP版）
  @”http://m.dbazure.net”
  ```

  * 说明：



