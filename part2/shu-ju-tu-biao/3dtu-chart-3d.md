# 3D图

#### 1、3D饼图

##### 数据属性DataSource结构：

```js
{
    datas:[{
        type: 'pie',
        name: '浏览器占比',
        data: [
            ['Firefox',   45.0],
            ['IE',       26.8],
            {
                name: 'Chrome',
                y: 12.8,
                sliced: true,
                selected: true
            },
            ['Safari',    8.5],
            ['Opera',     6.2],
            ['Others',   0.7]
        ]
    }],
    title:"测试饼图"
}

```

![](/assets/hchart20.png)

#### 2、3D柱状图

##### 数据属性DataSource结构：

```js
{
    datas:[{
        name: '小张',
        data: [5, 3, 4, 7, 2],
        stack: 'male'
    }, {
        name: '小王',
        data: [3, 4, 4, 2, 5],
        stack: 'male'
    }, {
        name: '小彭',
        data: [2, 5, 6, 2, 1],
        stack: 'female'
    }, {
        name: '小潘',
        data: [3, 0, 4, 4, 3],
        stack: 'female'
    }],
    title:"3D柱状图"
}

```

![](/assets/hchart21.png)

