<template lang="pug">
.-calculator.ui.container.segment
  .-form.ui.container.segment
    .ui.labeled.input
      .ui.label 現在年齡
      input(type="number" placeholder="40")
    .ui.labeled.input
      .ui.label 退休年齡
      input(type="number" placeholder="65")

    .ui.divider

    .ui.labeled.input
      .ui.label 現在薪資
      input(type="number" placeholder="300000")
    .ui.labeled.input
      .ui.label 退休開支
      input(tyue="number" placeholder="600000")

    .ui.divider

    .ui.labeled.input
      .ui.label 投資金額
      input(type="number" placeholder="3600000")
    .ui.labeled.input
      .ui.label 退休資產
      input(type="number" placeholder="10000000")

    .ui.divider

    .ui.labeled.input
      .ui.label 高風險資產
      input(type="number" placeholder="10")
    .ui.labeled.input
      .ui.label 低風險資產
      input(type="number" placeholder="6")

  line-chart(:chartdata='linedata', :options='options')

</template>

<script>
import LineChart from './LineChart.js'

export default {
  name: 'FIndCalculator',
  components: {
    LineChart
  },
  data() {
    return {
      linedata: {
        labels: [
          'January',
          'February',
          'March',
          'April',
          'May',
          'June',
          'July'
        ],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [40, 39, 10, 40, 39, 80, 40]
          }
        ]
      },
      options: { responsive: true, maintainAspectRatio: false }
    }
  }
}
</script>

<style scoped lang="sass">

.container
  display: flex
  flex-direction: column

.-form
  max-width: 25em !important
  flex-direction: column

.ui.segment
  margin-top: 2em
  margin-bottom: 1em

.input
  margin: .2em
</style>
