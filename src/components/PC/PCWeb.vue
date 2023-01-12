<template>
  <div>
    <div class="echarts-box">
      <div id="myEcharts" :style="{ width: '900px', height: '300px' }"></div>
    </div>
  </div>
</template>

<script>
import * as echarts from "echarts";
import * as axios from "core-js";
export default {
  name: "PCWeb",

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
          min: 10,
          max: 20
        },
        {
          show: false,
          type: 'continuous',
          seriesIndex: 1,
          min: 10,
          max: 20
        },
      ],
      xAxis: {
        data: [
          "今天",
          "周五",
          "周六",
          "周日",
          "周一",
          "周二",
          "周三",
          "周四",
          "周五",
          "周六",
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
            21,
            18,
            12,
            4,
            5,
            7,
            9,
            10,
            8,
            7,
          ],
          type: "line",
          smooth: true,
          markLine: {
            data: [{ type: 'average', name: 'Avg' }]
          },
          markPoint: {
            data: [{ name: '周最高', value: '21°C', xAxis: 0, yAxis: 21 }]
          },
        },
        {
          name: 'Lowest',
          data: [
            10,
            12,
            4,
            0,
            -1,
            -1,
            -1,
            1,
            0,
            1,
          ],
          type: "line",
          smooth: true,
          markLine: {
            data: [{ type: 'average', name: 'Avg' }]
          },
          markPoint: {
            data: [{ name: '周最低', value: '-1°C', xAxis: 4, yAxis: -1 }]
          },
        }
      ]
    });

    this.getData();
  },
  methods: {
    getData() { // 从服务的加载数的方法。
      // /static后什么不加，会被代理到http://tzb.xxu.edu.cn/dptt.htm
      axios.get()
          .then(e => {
            console.log(e)
          });
    }
  }
}
</script>


<style scoped>

</style>