# ts-react-echarts
Using typescript in the react to handle echarts application

#### 版本


```
 "react": "15.6.1",
 "typescript": "2.4.1",
```
#### 安装

```
npm i ts-react-echarts --save
```

#### 使用

```
import * as ECharts from 'echarts';
import {ReactECharts} from 'ts-react-echarts';


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