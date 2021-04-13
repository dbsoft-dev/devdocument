# GeoJSON地图

##### 作用：加载、展示GeoJSON格式的文件；可以自定义显示区域样式，处理点击事件；

#### 效果示例：

![](/assets/hchart22.png)

#### 数据源对象DataSource示例：

```js
{
    //数据源，需要显示的数据，必须！
    datas:[
        {name: '东方红农场', value: 1,aaa:[],bbb:{}},
        {name: '丰收镇', value: 3},
        {name: '新荒渔场', value: 1},
        {name: '红岗子乡', value: 2},
        {name: '太山镇', value: 2}
    ],
    //提示框个性设置
    // tooltip:{
    //     trigger: 'item',
    //     // formatter: '{b}<br/>{c}',
    //     formatter: function (params) {
    //         console.log(params.name+'<br/>'+a);
    //         var a = isNaN(params.value)?'':params.value;
    //         return params.name+'<br/>'+a;
    //     },
    // },

    //显示文本样式设置
    label:{
        formatter:'{b}\n{c}',
        formatter:function (params) {
            var a = isNaN(params.value)?'':params.value;
            return params.name+'\n'+a;
        },
        // backgroundColor:'blue',
    },
    //加载地图当前视角的缩放比例，默认为1；
    zoom:1.2,
    //滚轮缩放极限
    scaleLimit:{
        //最小缩放比例，默认为1；
        min:2,
        //最大缩放比例，默认为5；
        max:8
    },
    //值域选择
    dataRange:{
        show:false,
        // 值域颜色标识，颜色数组长度必须>=2，颜色代表从数值高到低的变化，即颜色数组低位代表数值高的颜色标识 ，支持Alpha通道上的变化（rgba）
        color:['red','yellow','blue'],
        // 指定的最小值，eg: 0，默认无，必须参数，唯有指定了splitList时可缺省min。
        min:0,
        // 指定的最大值，eg: 100，默认无，必须参数，唯有指定了splitList时可缺省max
        max:5,
    }
};
```



