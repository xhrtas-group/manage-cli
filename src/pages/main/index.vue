<template>
    <div class="mainPage">
        <div class="eachtsTest" ref="echart"></div>
    </div>
</template>

<script>
export default {
    name: '系统主页',
    methods: {
        drawChart () {
            // 基于准备好的dom，初始化echarts实例
            let myChart = this.$echarts.init(this.$refs.echart);
            // 指定图表的配置项和数据
            let option = {
                title: {
                    text: 'ECharts 入门示例'
                },
                tooltip: {},
                legend: {
                    data: ['销量']
                },
                xAxis: {
                    data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
                },
                yAxis: {},
                series: [
                    {
                        name: '销量',
                        type: 'bar',
                        data: [5, 20, 36, 10, 10, 20]
                    }
                ]
            };
            // 使用刚指定的配置项和数据显示图表。
            myChart.setOption(option);
        }
    },
    mounted () {
        this.drawChart();
    }
};
</script>

<style lang="less" scoped>
    .mainPage{
        width: 100%;
        height: 100%;
        .eachtsTest{
            width: 50%;
            height: 50%;
        }
    }
</style>
