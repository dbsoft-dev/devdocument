# 全局对象-app.SecurityContext

说明：在程序的任何地方都可以访问到app. SecurityContext这个全局的安全上下文对象。

* ##### 属性：LoginUser

  * 类型：对象；
  * 说明：砚台用户信息对象，如果是通过微信浏览器打开页面，LoginUser对象保存着用户的微信相关信息。

### LoginUser对象的属性说明（通过微信浏览器登录时获取）

##### \_id：砚台注册用户\_id

##### LoginName：登录账号

##### UserName：用户的微信昵称

##### Sex：用户的性别

##### HeadImgUrl：用户头像，用户没有头像时该项为空。若用户更换头像，原有头像URL将失效。

##### WXUId：只有在将公众号绑定到微信开放平台帐号后，才会出现该字段。

##### OpenId：用户的唯一标识

##### WPId：微信公众号的原始Id

##### Country：国家

##### Province：省份

##### City：城市



### LoginUser对象的属性说明（通过砚台登录时获取）

##### \_id：砚台注册用户id

##### LoginName：登录账号

##### UserName：用户名

##### NickName：用户的昵称

##### HeadImgUrl：用户头像，用户没有头像时该项为空。若用户更换头像，原有头像URL将失效。

##### Mobile：电话号码

##### CreateDate：注册时间

##### BirthDay：生日



