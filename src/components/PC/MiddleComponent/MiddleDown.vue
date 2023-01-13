<template>
  <div style="width: 33%;height: 30rem;background: #051336">
      <div id="myEcharts" :style="{ width: '60rem', height: '100%' }"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "LeftDown",
  mounted() {
    echarts.init(document.getElementById("myEcharts"), "dark").setOption({
      title: [
        {
          top: '5%',
          left: 'center',
          text: '10日温度预报'
        },
      ],
      visualMap: [
        {
          show: false,
          type: 'continuous',
          seriesIndex: 0,
          min: 5,
          max: 15
        },
        {
          show: false,
          type: 'continuous',
          seriesIndex: 1,
          min: 5,
          max: 15
        },
      ],
      xAxis: {
        data: [
          "今天",
          "周六",
          "周日",
          "周一",
          "周二",
          "周三",
          "周四",
          "周五",
          "周六",
          "周日",
        ]
      },
      yAxis: {
        type: 'value',
        axisLabel: {
          formatter: '{value} °C'
        }
      },
      tooltip: {
      },
      series: [
        {
          name: 'Highest',
          data: [
            18,
            12,
            4,
            5,
            7,
            9,
            10,
            8,
            9,
            8
          ],
          type: "line",
          smooth: true,
          markLine: {
            data: [{ type: 'average', name: 'Avg' }]
          },
          markPoint: {
            data: [{ name: '周最高', value: '18°C', xAxis: 0, yAxis: 18 }]
          },
        },
        {
          name: 'Lowest',
          data: [
            12,
            4,
            0,
            -2,
            -1,
            -2,
            1,
            0,
            0,
            2
          ],
          type: "line",
          smooth: true,
          markLine: {
            data: [{ type: 'average', name: 'Avg' }]
          },
          markPoint: {
            data: [{ name: '周最低', value: '-2°C', xAxis: 3, yAxis: -2 }]
          },
        }
      ]
    });


  },

}
</script>

<style scoped>

</style>