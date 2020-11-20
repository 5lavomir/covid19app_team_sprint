<template>
  <div>
    <div class='chart-wrapper'><chart :options='chartOptionsBar'></chart></div>
    <hr />
    <div class='chart-wrapper'>
      <chart :options='chartOptionsLine'></chart>
    </div>
  </div>
</template>

<script>
export default {
  name: 'graph',
  data: () => ({
    chartOptionsLine: {
      xAxis: {
        data: [
          'Jan',
          'Feb',
          'Mar',
          'Apr',
          'May',
          'Jun',
          'Jul',
          'Aug',
          'Sep',
          'Oct',
          'Nov',
          'Dec'
        ]
      },
      yAxis: {
        type: 'value'
      },
      series: [
        {
          type: 'line',
          data: [55, 72, 84, 48, 59, 62, 87, 75, 94, 101, 127, 118]
        }
      ],
      title: {
        text: 'Monthly Stock Prices',
        x: 'center',
        textStyle: {
          fontSize: 24
        }
      },
      color: ['#127ac2']
    }
  })
}
</script>

<style scoped>
.chart-wrapper {
  width: 100%;
  height: 700px;
}
.echarts {
  width: 100%;
  height: 100%;
}
</style>
