# ts-react-echarts
Using typescript in the react to handle echarts application

#### 版本


```
 "react": "15.6.1",
 "typescript": "2.4.1",
```


#### 依赖

```
    "@types/echarts": "0.0.6",
    "@types/element-resize-event": "2.0.0",
    "@types/react": "15.0.36",
    "@types/react-dom": "15.5.1",
    "echarts": "^3.6.2",
    "element-resize-event": "^2.0.9",
    "react": "^15.6.1",
    "react-dom": "^15.6.1"
```
#### 安装
```
Copy to the plug-in directory, and import
import {ReactECharts} from '../../plugins/ts-react-echarts';
```

#### 使用

```
import * as ECharts from 'echarts';
import {ReactECharts} from '../../plugins/ts-react-echarts';


const option:ECharts.EChartOption = {
    

    tooltip : {
        trigger: 'item'
    },

    series : [
        {
            name: '访问来源',
            type: 'pie',
            radius : '55%',
            center: ['50%', '50%'],
            data: [
                {value: 335, name: '直接访问'},
                {value: 310, name: '邮件营销'},
                {value: 274, name: '联盟广告'},
                {value: 235, name: '视频广告'},
                {value: 400, name: '搜索引擎'}
            ],
            roseType: 'angle',
            label: {
                normal: {
                    textStyle: {
                        color: '#777'
                    }
                }
            },
            labelLine: {
                normal: {
                    lineStyle: {
                        color: '#777'
                    },
                    smooth: 0.2,
                    length: 10,
                    length2: 20
                }
            },
            itemStyle: {
                normal: {
                    color: '#c23531',
                    shadowBlur: 200,
                    shadowColor: '#777'
                }
            },

            animationType: 'scale',
            animationEasing: 'elasticOut',
            animationDelay: function () {
                return Math.random() * 200;
            }
        }
    ]
};


class App extends React.Component<{}, {}> {
    render() {
        return (
            <div>
               <ReactECharts  option = {option}  name="dddd"/>
            <div/>
        )
    }
    
}

```