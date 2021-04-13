# 饼图

#### 数据源属性DataSource数据结构：

```js
{
    title:"测试图表标题",//图表标题，可以在设计界面直接设置；
    subtitle:"这是副标题",//图表副标题，可以在设计界面直接设置；
//颜色序列，依次取值，循环使用；不给定则使用默认系
colors:["#333","#666","#123"],
//内环半径大小 默认为0，字符串，可以是百分数、**px值；
innerSize:"50%",
    //显示数据-数组
    datas:    [{
        name: 'Chrome',
        y: 61.41,
        sliced: true,
        selected: true
    }, {
        name: 'Internet Explorer',
        y: 11.84
    }, {
        name: 'Firefox',
        y: 10.85
    }, {
        name: 'Edge',
        y: 4.67
    }, {
        name: 'Safari',
        y: 4.18
    }, {
        name: 'Sogou Explorer',
        y: 1.64
    }, {
        name: 'Opera',
        y: 1.6
    }, {
        name: 'QQ',
        y: 1.2
    }, {
        name: 'Other',
        y: 2.61
    }]
};

```

#### 饼图

![](/assets/hchart09.png)

#### 环形图

![](/assets/hchart10.png)

