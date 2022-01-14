<template>
  <div style="padding: 10px">
    <el-card>
      <div id="myChart" :style="{width: '800px', height: '600px'}"></div>
    </el-card>
  </div>
  <div>
    <el-table :data="tableData" style="width: 100%">

      <el-table-column prop="API" label="API" width="195" />
      <el-table-column prop="Example" label="Example" width="270"/>
    </el-table>
    </div>

</template>

<script>
import request from "@/utils/request";

export default {
  name: "Home",
  data() {
      return {
        tableData: [
          {
            API: 'http:/localhost:9876/find/',
            Example: 'http:/localhost:9876/find/algorithm/Alignment',
          },
        ],
      }
    },

  mounted() {
    this.drawLine();
  },

  methods: {
    drawLine() {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$root.echarts.init(document.getElementById('myChart'))
      let option = {
        title: {
          text: '算法统计图',
          subtext: '虚拟数据',
          left: 'left'
        },
        tooltip: {
          trigger: 'item'
        },
        legend: {
          trigger: 'item'
        },
        toolbox: {
          show: true,
          feature: {
            mark: {show: true},
            dataView: {show: true, readOnly: false},
            restore: {show: true},
            saveAsImage: {show: true}
          }
        },
        series: [
          {
            name: '算法比例',
            type: 'pie',
            radius: [50, 250],
            center: ['50%', '50%'],
            roseType: 'area',
            itemStyle: {
              borderRadius: 8
            },
            data: []
          }
        ]
      }
      request.get("/user/count").then(res => {
        if (res.code === '0') {
          res.data.forEach(item => {
            option.series[0].data.push({name: item.address, value: item.count})
          })
          // 绘制图表
          myChart.setOption(option);
        }
      })

    }
  }


}
</script>






<style scoped>

</style>




