# 地图控件 Map

###### 作用：加载、显示高德地图；

高德地图 文档：[https://lbs.amap.com/api/javascript-api/summary](https://lbs.amap.com/api/javascript-api/summary)

### 设计属性

* ##### 对象名称

  * 类型：字符串；

  * 值：

  * 说明：自定义控件对象名；
* ##### 地图类型

  * 类型：（下拉选项）；

  * 值：默认值：普通地图；

  * 说明：可选值：普通地图、简易国家地图、简易省图、简易世界地图；
* ##### 地图样式

  * 类型：（下拉选项）；

  * 值：默认值：标准；

  * 说明：设置地图显示外观样式；可选值：标准、马卡龙等；
* ##### 缩放级别

  * 类型：数值；

  * 默认值：默认值:3；

  * 说明：取值范围：PC：\[3,18\]; App:\[3,19\]；
* ##### 定位当前位置

  * 类型：（单选框）；

  * 说明：是否定位当前位置；
* ##### 工具栏

  * 类型：（单选框）；

  * 说明：是否显示工具栏；
* ##### 区域面

  * 类型：（单选框）；

  * 说明：是否显示区域面；
* ##### 道路

  * 类型：（单选框）；

  * 说明：是否显示道路；
* ##### 建筑物

  * 类型：（单选框）；

  * 说明：是否显示建筑物；
* ##### 卫星图层

  * 类型：（单选框）；

  * 说明：是否显示卫星图层；
* ##### 路网图层

  * 类型：（单选框）；

  * 说明：是否显示路网图层；
* ##### 工具条

  * 类型：（单选框）；

  * 说明：是否显示工具条；
* ##### 比例尺

  * 类型：（单选框）；

  * 说明：是否显示比例尺；
* ##### 鹰眼

  * 类型：（单选框）；

  * 说明：是否显示鹰眼；
* ##### 地图切换

  * 类型：（单选框）；

  * 说明：是否显示地图切换；
* ##### 标注

  * 类型：（单选框）；

  * 说明：是否显示标注；
* ##### 拖拽平移

  * 类型：（单选框）；

  * 说明：是否支持拖拽平移；
* ##### 双击放大

  * 类型：（单选框）；

  * 说明：是否支持双击放大；
* ##### 支持缩放

  * 类型：（单选框）；

  * 说明：是否支持支持缩放；

### 事件处理程序

* ##### MarkedPosition

  * 调用时机：标记位置结束时调用；
  * 说明：
* ##### MapComplete

  * 调用时机：地图加载完成调用；
  * 说明：
* ##### MarkerClick

  * 调用时机：点击标记点时调用；
  * 说明：此事件中可以获取标记对象ClickedMarker、标记数据对象ClickedMarkerData；
* ##### POIListItemClick

  * 调用时机：点击兴趣点搜索结果列表中的item时调用；
  * 说明：可在此事件中获取兴趣点信息POIItemInfo；
* ##### LiveLocation

  * 调用时机：每间隔一段时间（默认30秒）调用一次；
  * 说明：在此事件中可通过地图控件对象的属性CurrentPosition实时获取当前的位置信息；属性CurrentPosition为对象类型，它的属性status等于0时定位失败，否则定位成功，可以获取当前位置的经纬度信息。
* ##### MapComplete

  * 调用时机：地图加载完成调用；
  * 说明：
* ##### PlaceSearchCompleted

  * 调用时机：调用搜索地址的方法PlaceSearchNearBy\(\)或SearchPlace\(\)后，搜索操作完成时；
  * 说明：此事件中可以通过控件的属性SearchResults获取到搜索地址集合；
* ##### SearchResultSelect

  * 调用时机：选中搜索结果列表中的某一个地址时；
  * 说明：此事件中可以通过控件的属性SearchResult获取到选中的地址信息对象；
* ##### GetDistrictData

  * 调用时机：调用搜索行政区方法获取到行政区数据后；
  * 说明：此事件中可以通过控件对象的属性DistrictList获取到选择的行政区下属行政区对象集合;

### 属性、方法

* ##### DrawDisProvince\(config\)-方法，绘制省级及以下行政区图；

  * 说明：参数config为参数对象，格式：{adcode:"220100",depth:3}
    adcode-省\(市\)行政区编码；depth-显示层级深度，0-省级；1-市级；2-区/县级；
* * 示例：
  * ```js
    Map.DrawDisProvince({adcode:"220100",depth:3});//Map为控件对象
    ```
* ##### ClickedMarker-属性，获取点击的标记对象；

  * 说明：对象，在事件MarkerClick中可以获取此对象；该对象有属性DataContext保存着创建标记时传递数据对象；
* * 示例：
  * ```js
    var marker = Map.ClickedMarker；//Map为控件对象
    ```
* ##### SearchDistrict\(adcode,level\)-方法，搜索行政区；

  * 说明：获取到搜索结果后，触发GetDistrictData事件；
    adcode-行政区名、citycode、adcode；level-设置关键字对应的行政区级别或商圈，可选值：country：国家；province：省/直辖市；city：市；district：区/县biz\_area：商圈；官方文档：[https://lbs.amap.com/api/javascript-api/reference/search\#m\_AMap.DistrictSearch](https://lbs.amap.com/api/javascript-api/reference/search#m_AMap.DistrictSearch)
* * 示例：
  * ```js
    Map.SearchDistrict('吉林省','city');//Map为控件对象
    ```
* ##### DistrictList-获取行政区对象集合；

  * 说明：在事件GetDistrictData中获取到行政区对象集合；
* * 示例：
  * ```js
    var districtList = Map.DistrictList；//Map为控件对象
    ```
* ##### aMap-属性，获取高德地图对象；

  * 说明：获取高德地图对象，使用此地图对象可以调用高德地图原生属性和方法；
* * 示例：
  * ```js
    var aMap = Map.aMap;//Map为控件对象
    ```
* ##### ClickedMarkerData-属性，点击路径上标记点的数据对象；

  * 说明：对象，点击标记时，在事件MarkerClick中获取点击的标记数据对象；
* * 示例：
  * ```js
    //数据格式：{title:"",label:"",lng:"",lat:""}
    var markerData = Map.ClickedMarkerData；//Map为控件对象
    ```
* ##### DrawTruckShortPath\(points,cb\)-绘制最短货车路径；

  * 说明：参数points为地点信息对象point\(point对象的格式参见下表2\)数组；cd为路径绘制后的回调函数，第一个参数status-绘制状态，第二个参数result-绘制的结果数据信息；
* * 示例：
  * ```js
    Map.DrawTruckShortPath ([{ lat: 43.893875,lng: 125.276242},{ lat: 43.893875,lng: 125.276242}],function(status,result){})；//Map为控件对象
    ```
* ##### LoadMarkers\(points\)-方法，绘制点标记；

  * 说明：参数points为地点信息对象point\(point对象的格式参见下表2\)数组；
* * 示例：
  * ```js
    Map.LoadMarkers([{ lat: 43.893875,lng: 125.276242},{ lat: 43.893875,lng: 125.276242}]);//Map为控件对象
    ```
* ##### SearchResult-属性，选中的搜索结果对象；

  * 说明：对象；
* * 示例：
  * ```js
    var searchResult = Map.SearchResult；//Map为控件对象
    //格式：
    {adcode: "220104"，address: "前进大街2326号"，city: []，district: "吉林省长春市朝阳区"，id: "B0FFG6TRRI"，location: {P: 43.827406, R: 125.29028199999999, lng: 125.290282, lat: 43.827406}，name: "修正服务外包大厦(西门)"}
    ```
* ##### SearchResults，搜索结果集；

  * 说明：数组，在事件PlaceSearchCompleted执行并成功获取搜索结果时，此属性有值，否则为空集合；
* * 示例：
  * ```js
    var searchResults = Map.SearchResults;//Map为控件对象
    ```
* ##### SearchPlace\(kw\)-搜索地址；

  * 说明：参数kw字符串，为需要检索的地址信息；
* * 示例：
  * ```js
    Map.SearchPlace('吉林省长春市人民广场');//Map为控件对象
    ```
* ##### CurrentPosition，获取当前位置信息；

  * 说明：在事件LiveLocation中可以实时的获取当前的位置信息对象。格式参照下表CurrentPosition对象格式；
  * 示例：

  ```
  var currentPosition = Map.CurrentPosition;//Map为控件对象
  ```

* ##### MarkPosition-属性，获取标记位置信息对象；

  * 说明：在标记位置信息时获取。对象格式：{ lat: 43.893875,lng: 125.276242}    lng:经度，lat：纬度；
* * 示例：
  * ```js
    var markPosition = Map.MarkPosition；//Map为控件对象
    ```
* ##### DrawDrivingRoute\(points,policy,cb\)-方法，绘制驾车路线；

  * 说明：通过指定点按照顺序绘制驾车路线，**参数points**为指定点位置对象的集合，指定点位置对象格式：{ lat: 43.893875,lng: 125.276242}, lng:经度，lat：纬度；**参数policy**为路径规划策略，数值：1-最快捷模式\(默认\)，2-最经济模式，3-最短距离模式，4-考虑实时路况，不传为默认1；**cd**为路径绘制后的回调函数，第一个参数status-绘制状态，第二个参数result-绘制的结果数据信息。
* * 示例：
  * ```js
    //Map为控件对象
    Map.DrawDrivingRoute([{ lat: 43,lng: 125},{ lat: 43.5,lng: 124},{ lat: 43.8,lng: 123 }]);
    ```
* ##### DrawTruckRoute\(points,policy,cb\)-方法，绘制货车路线；

  * 说明：通过指定点按照顺序绘制货车路线，参数points为指定点位置对象的集合，指定点位置对象格式：{ lat: 43.893875,lng: 125.276242}, lng:经度，lat：纬度。参数policy为路径规划策略，数值：1-9，不传为默认1；cd为路径绘制后的回调函数，第一个参数status-绘制状态，第二个参数result-绘制的结果数据信息；
* * 示例：
  * ```js
    //Map为控件对象
    Map.DrawTruckRoute([{ lat: 43,lng: 125},{ lat: 43.5,lng: 124},{ lat: 43.8,lng: 123 }]);
    ```
* ##### PlaceSearchNearBy\(config,keyword\)-方法，搜索附近兴趣点；

  * 说明：keyword：字符串，搜索用关键字；如果不传递此参数，则config中的字段都需要配置，如果此参数有值，则config中的字段可选择性配置；
  * 参数config结构：

  ```js
  {
         //可选，兴趣点类型 多个用|分隔
         type:"餐饮|酒店|电影院",
         //可选，每页显示数据数，默认5
         pageSize:5,
         //默认显示页数，1-100
         pageIndex:1,
         //兴趣点城市码
         city:"010",
         //是否自动调整地图视野使绘制的 Marker点都处于视口的可见范围
         autoFitView:true,
         //LngLat-中心点坐标
         cpoint:[116.405467, 39.907761],
         //搜索半径 取值范围0-50000
         radius:2000,
         panel:显示搜索结果的容器对象,
     }
  ```
* * 示例：
  * ```js
    Map.PlaceSearchNearBy(config，keyword);//Map为控件对象
    ```
* ##### POIItemInfo-属性，兴趣点信息；

  * 说明：此属性值只有在POIListItemClick事件中获取才有值，对象类型，包含信息见图Poi基本信息和Poi详细信息；
* * 示例：
  * ```js
    var pOIItemInfo = Map.POIItemInfo；//Map为控件对象
    ```
* ##### Config-配置地图样式信息；

  * 说明：参数points为地点信息对象point\(point对象的格式参见下表2\)数组；cd为路径绘制后的回调函数，第一个参数status-绘制状态，第二个参数result-绘制的结果数据信息；
* * 示例：
  * ```js
    //Map为控件对象
    //1、简易国家地图：
    //SOC: SOC字段设定显示的国家；参照：高德地图：国家与地区SOC
    //depth：depth字段设定数据的层级深度，depth为0的时候只显示国家面，depth为1的时候显示省级，当国家为中国时设置depth为2的可以显示市一级。
    Config = {
      SOC: 'CHN',
      depth:1
    }
    //2、简易省图：
    //adcode: 行政区的adcode。参照：高德地图：adcode行政区编码与城市编码表。
    //depth: depth字段设定数据的层级深度，depth为0的时候只显示省面，depth为1的时候显示市级，当depth为2的可以显示县一级
    Config = {
      adcode: '130000',
      depth:1
    }
    ```
* ##### HeatMapData-配置热力图数据；

  * 说明：options：热力图绘制配置参数；data：显示的数据集；max:数据count的最大值
* * 示例：
  * ```js
    //Map为控件对象
    Map.HeatMapData={
        options:{
            radius: 25, //给定半径
            opacity: [0, 0.8],//透明度范围
            gradient: {         //设置渐变色
                0.5: 'blue',
                0.65: 'rgb(117,211,248)',
                0.7: 'rgb(0, 255, 0)',
                0.9: '#ffea00',
                1.0: 'red'
            }},
        data: [{
            "lng": 116.191031,//经度值
            "lat": 39.988585,//纬度值
            "count": 10       //数值
        }, {
            "lng": 116.389275,
            "lat": 39.925818,
            "count": 11
        },……],
        max: 20             //最大值
    };
    ```
* ##### SearchResult-属性，选中的搜索结果对象；

  * 说明：对象；
* * 示例：
  * ```js
    var searchResult = Map.SearchResult；//Map为控件对象
    //格式：
    {adcode: "220104"，address: "前进大街2326号"，city: []，district: "吉林省长春市朝阳区"，id: "B0FFG6TRRI"，location: {P: 43.827406, R: 125.29028199999999, lng: 125.290282, lat: 43.827406}，name: "修正服务外包大厦(西门)"}
    ```
* ##### SearchResults，搜索结果集；

  * 说明：数组，在事件PlaceSearchCompleted执行并成功获取搜索结果时，此属性有值，否则为空集合；
* * 示例：
  * ```js
    var searchResults = Map.SearchResults;//Map为控件对象
    ```
* ##### SearchPlace\(kw\)-搜索地址；

  * 说明：参数kw字符串，为需要检索的地址信息；
* * 示例：
  * ```js
    Map.SearchPlace('吉林省长春市人民广场');//Map为控件对象
    ```



#### _附表：_

##### 1、CurrentPosition对象属性：

* ##### status

  * 类型：数值；

  * 说明：0-定位失败；1-定位成功；
* ##### type

  * 类型：字符串；

  * 说明：失败时-"error"；成功时，显示定位结果的来源，可能的值有:'html5'、'ip'、'sdk'；

* ##### message

  * 类型：字符串；

  * 说明：形成当前定位结果的一些信息；
* ##### info

  * 类型：字符串；

  * 说明：状态信息："FAILED"-失败；"SUCCESS"-成功；

* ##### lng

  * 类型：数值；

  * 说明：成功时的位置经度值；
* ##### lat

  * 类型：数值；

  * 说明：成功时的位置纬度值；

##### 2、point对象格式：

* ##### lng

  * 类型：数值；

  * 说明：位置的经度值，必需；
* ##### lat

  * 类型：数值；

  * 说明：位置的纬度值，必需；

* ##### title

  * 类型：字符串；

  * 说明：鼠标经过点标记时显示的文字，可选；
* ##### label

  * 类型：字符串；

  * 说明：点标记旁边的显示文字，可选；

* ##### c

  * 类型：字符串；

  * 说明：label显示文字的颜色，可选；
* ##### bgc

  * 类型：字符串；

  * 说明：label的背景颜色，可选；

* ##### icon

  * 类型：字符串；

  * 说明：点标记显示图片的地址，可选；
* ##### w

  * 类型：字符串；

  * 说明：点标记图片的宽度，可选；

* ##### h

  * 类型：字符串；

  * 说明：点标记图片的高度，可选；

![](/assets/poi01.png)

![](/assets/poi02.png)

