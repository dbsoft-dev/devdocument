# HChart数据图表

#### 基础教程：[https://www.highcharts.com.cn/docs](https://www.highcharts.com.cn/docs)

#### 图表基本组成：

#### ![](/assets/hchart01.png)数据源属性DataSource，类型：对象；基础数据结构：

```js
{
    //必需!显示数据-数组类型，绘制折线或柱状图的组数由数组元素个数决定；
    datas:[{
        //图表分组名称
        name: '安装，实施人员',
        //图表每组数据；某个数据点不绘制时，赋值为null；
        data: [43934, 52503, 57177, 69658, 97031, 119931, 137133, 154175]
    }, {
        name: '工人',
        data: [24916, 24064, 29742, 29851, 32490, 30282, 38121, 40434]
    }, {
        name: '销售',
        data: [11744, 17722, 16005, 19771, 20185, 24377, 32147, 39387]
    }, {
        name: '项目开发',
        data: [null, null, 7988, 12169, 15112, 22452, 34400, 34227]
    }, {
        name: '其他',
        data: [12908, 5948, 8105, 11248, 8989, 11816, 18274, 18111]
    }],

    //可选参数；颜色序列，依次取值，循环使用；不给定则使用默认颜色系;
    //默认颜色系：['#7cb5ec', '#434348', '#90ed7d', '#f7a35c', '#8085e9',
    //'#f15c80', '#e4d354', '#2b908f', '#f45b5b', '#91e8e1']
    colors:["#333","#666","#123"],

    //可选参数；图表标题，可以在开发平台设计界面直接设置；
    title:"图表标题",
    //可选参数；图表副标题，可以在开发平台设计界面直接设置；
    subtitle:"副标题",

    //x轴显示文本数组；
    xLabels:["1月","2月","3月","4月","5月","6月","7月","8月"],

    //可选；x轴样式设置
    xAxis: {
        //横坐标绘制间距
        tickInterval: 1,
        //轴线颜色
        lineColor:"#333",
        //轴线宽度
        lineWidth:1,
        //坐标轴标签样式设置
        labels:{
            rotation:60,//x轴label旋转角度
            style:{
                color:"#272d35",//x轴label文字颜色；
                "fontSize": "11px",
            }
        },
    },

    //y轴标题
    yTitle:"y坐标",

//设定图例项的CSS样式。只支持有关文本的CSS样式设定。 默认是：{ "color": "#333333", "cursor": "pointer", "fontSize": "12px", "fontWeight": "bold" }.
legend:{
    itemStyle:{
        fontSize:"12px"
    },
    //设定每个图例项的宽度。当图例有很多图例项，并且用户想要这些图例项在同一平面内垂直对齐，此时这个属性可帮用户实现此效果。
    itemWidth:"80px",
    //图例数据项的布局。布局类型： "horizontal" 或 "vertical" 即水平布局和垂直布局 默认是：horizontal.
    layout:'horizontal',
    // 图例容器是否可以浮动，当设置为浮动（true）时，图例将不占用绘图区空间，并可以层叠在图形上方。 默认是：false.
    floating:false,
},

    //可选；数据提示框样式；数据提示框指的当鼠标悬停在某点上时，以框的形式提示该点的数据
    //
    tooltip: {
        //标题格式化
        headerFormat: '<span style="font-size:11px">{series.name}</span><br>',
        //数据点格式化字符串
        pointFormat: '<span style="color:{point.color}">{point.category}</span>: <b>{point.y}</b> <br/>',
        //背景色
        backgroundColor:"#272d35",
        //边框颜色
        borderColor:"#fff",
        //边框圆角半径 默认值3
        borderRadius:3,
        //边框宽度，默认值1
        borderWidth:1,
        //是否启用数据点提示框。 默认是：true.
        enabled: true,
        //是否使用HTML代码渲染提示框的内容用以代替SVG。使用HTML允许高级格式化，如在提示框中使用表格和图像。 默认是：false.
        useHTML: false,
        //数据提示框数据值小数保留位数。可以在每个数据列的 tooltip 对象中针对某个数据列单独设置。默认为保留所有小数。
        valueDecimals:"",

    },
    //可选；数据列配置
    plotOptions: {
        // 仪表盘图表数据列样式
        solidgauge: {
            //数据标签样式
            dataLabels: {
                //是否显示
                enabled: true,
                //数据标签格式化
                formatter:function () {
                    //this对存储当前数据列的相关信息
                    //this.percentage-当前数据列占总和的百分比
                    //this.point-点对象，this.point.name；
                    //this.series-序列对象，this.series.name;
                    // this.total-数据总和；
                    // this.x-x值；
                    // this.y-y值；
                    return this.y+"%";
                },
                //边框宽度
                borderWidth:0,
                //标签文字样式
                style:{
                    fontSize:"68px",
                    color:"red",
                    fontWeight:"bold",
                    textOutline:"1px 1px contrast",
                },
                //水平对齐方式；可以用的值有 "left", "center" 或 "right"。
                align:"center",
                //垂直对齐方式；可以用的值有 "top", "middle" 或 "bottom"。
                verticalAlign:"middle",
            },
            //线两端形状round-圆头、square-方形
            linecap: 'square',
            stickyTracking: false
        }
    },


    //可选；面板样式设置，只针对仪表盘图表和极地图；
    pane: {
        //极地图 x 轴或仪表图值轴的结束角度，为角度值，即 0 表示图形的正北方向。默认值为 0。
        startAngle: 0,
        //极地图 x 轴或仪表图 y 轴（值轴）的结束角度，为角度值，即 0 表示图形的正北方向。默认值是在开始角度（ startAngle）的基础上 + 360度。
        endAngle: 360,
        // 面板背景相关配置。
        background: [{
            //面板背景的内、外半径，可以是数值（像素） 或百分比字符串。 默认是：0
            outerRadius: '100%',
            innerRadius: '88%',
            // 面板的背景颜色，可以是 渐变颜色。
            backgroundColor: 'red',
            // 面板背景边框宽度 默认是：1.
            borderWidth: 0
        }]
    },


}
```



