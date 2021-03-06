# 属性编辑器 PropertyEditor

作用：动态生成表单编辑列表；

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；

### 属性、方法

* ##### Columns-属性，设置显示列数；

  * 说明：数值；
* * 示例：
  * ```js
    PropertyEditor.Columns = 2;//PropertyEditor为控件对象
    ```
* ##### ProMapList-属性，设置表单显示的编辑器列表；

  * 说明：对象；
* * 示例：
  * ```js
    //PropertyEditor为控件对象
    peditor.ProMapList = {
        Text: "医生信息", ImageUrl: "", MinWidth:'180px',
        Items: [{  DP: "Name", IsNull: 0, TipText:"输入医生名称",Suffix:"年", EA:1, ET: "text", Format: "", Category: "基本信息" },
            { Text: "性别", DP: "Sex", EA:1, ET: "Select", Format: "", Items: [{ Text: "女", Value: "1" },{ Text: "男", Value: "2" },{ Text: "保密", Value: "3" }], Category: "基本信息" },
            { Text: "生日", DP: "Birthday", EA: 1, ET: "date", Format: "", Category: "基本信息",Max:'2025-03-02',Min:'1990-02-01' },
            { Text: "工作年限", DP: "WorkYear", TipText: "输入参加工作年限",Suffix:"年", IsNull: 0, EA: 1, ET: "number", Format: "", Category: "职业信息" },
            { Text: "喜欢色彩", DP: "FavColor", EA: 1, ET: "color", Format: "", Category: "职业信息" },
            { Text: "电话", DP: "Mobile", TipText: "输入医生移动电话", WrongTip:'请输入合格的电话号码！',IsNull: 0, EA: 1, ET: "tel", Format: "", Category: "职业信息" ,VR:"MPhoneID"},
            { Text: "Email", DP: "Email", EA: 1, ET: "email", Format: "", Category: "职业信息" },
            { Text: "在职", DP: "OnDuty", EA: 1, ET: "checkbox", Format: "", Category: "职业信息" },
            { Text: "现任职务", DP: "Job", EA: 1, ET: "ListBox", Columns: 2, Type: "radio", Format: "", Items: [{ Text: "总经理", Value: "总经理" }, { Text: "部门经理", Value: "部门经理" }, { Text: "程序员", Value: "程序员" }], Category: "职业信息" },
            { Text: "兴趣爱好", DP: "Preference", EA: 1, ET: "ListBox", Columns: 1, Type: "checkbox", Format: "", Items: [{ Text: "看书", Value: "1" }, { Text: "听音乐", Value: "2" }, { Text: "旅行", Value: "3" }], Category: "职业信息" },
            { Text: "每日看书时间", DP: "BookTime", TipText: "选择看书时间",Suffix:"年", IsNull: 0, EA: 1, ET: "range", Format: "", Min: 0, Max: 600, Step: 10,  Category: "职业信息" },
            { Text: "自我介绍", DP: "Intro", TipText: "输入自我介绍", IsNull: 0, EA: 1, ET: "RTBox", Format: "",ColSpan:2,Category: "职业信息" },
            { Text: "创建时间", DP: "CreTime", EA: 1, ET: "datetime-local", Format: "",Max:'2025-03-02T00:00:00',Min:'1990-02-01T12:00:00'},
            { Text: "删除时间", DP: "DelTime", EA: 1, ET: "datetime-local", Format: "",Category: "信息"},
            { Text: "配图", DP: "ImageUrl", EA: 1, ET: "Image", Format: ""},
          ]
      };
    ```

#### ProMapList各个字段说明：

##### Text：字符串，显示文本；

##### ET：字符串，控件类型；text-文本输入框；Select-下拉选；date-日期选择；time-时间选择；datetime-local-日期加时间选择；number-数值输入；color-颜色选择；email-电子邮件输入框；checkbox-单选列表；ListBox-选择列表，需要设置Type，Type为checkbox时，可多选，Type为radio时单选；range-进度条，设置最大最小值和实际值；RTBox-富文本输入框，可复制带格式的内容； Image-图片选择框；

##### ImageUrl：字符串，显示图片地址；

##### DP：字符串，数据属性，和DataContext字段对应时即可显示、获取值；

##### IsNull：数值，是否为必填项，0-必填，显示红色的星星，不设置或者其他非0值，非必填项；

#####  TipText：字符串，ET为输入类型控件时，显示的提示文字；

#####  Category：字符串，设置当前控件所在分组，分组值相同的会显示在同一组；没有此字段的自动分在一组；值为组头显示的文本；

#####  EA：数值，1-可编辑； 

#####  Format：字符串，设置格式化显示文本；

##### Items：数组，ET为Select、checkbox、ListBox时，设置可选项，结构为\[{ Text: "女", Value: "1" },{ Text: "男", Value: "2" },{ Text: "保密", Value: "3" }\]； 

##### ColSpan：数值，ET为RTBox时，设置输入框所占列数；

##### VR：字符串，验证规则，设置输入数据的验证规则；

##### WrongTip:字符串，错误提示 ；

注：

1、ET为range时，还可设置Min-数值，最小值；Max-数值，最大值；Value-默认值；Step-数字间隔，使用键盘或者鼠标拖动时，移动的数字加减间隔；

2、ET为color时，颜色值必须为16进制格式颜色字符串，例：\#FFFFFF；

3、ET为时间类型时，可以设置Max-最大可选日期，Min-最小可选日期，结构需要和ET接受的结构相同，例如ET为datetime-local时，Max值结构为2025-03-02T00:00:00；

* ##### DataContext-属性，设置/获取编辑器数据上下文；

  * 说明：对象，各个字段和ProMapList中字段DP对应；
* * 示例：
  * ```js
    //PropertyEditor为控件对象
    PropertyEditor.DataContext = {
         Birthday: "1997-07-01", WorkYear: 1, FavColor: "#ff0000",BookTime:2, Mobile: "13877778888",
        Email: "13877778888@qq.com", Job: { Values: ["总经理"] }, Preference: { Values: ["1","2"]}};
    ```

##### 



