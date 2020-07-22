<script>
import { Line } from 'vue-chartjs'

/*
Instructions:
Update Chart component to receive an array of objects as a prop e.g [ { label: 2016, value: 0 }, { label: 2017, value: 4 }]
Update chartDataConfig.labels to be an array of strings, using the lablels in the prop
Update chartDataConfig.datasets to contain one object whose property 'data' is an array of numbers, using the values in the prop
*/

export default {
  extends: Line,
  props: ['chartData'],
  data() {
    return {
      chartDataConfig: {
        labels: [],
        datasets: [
          {
            data: [],
          },
        ],
      },
      options: {},
    }
  },
  mounted() {
    this.renderChart(this.chartDataConfig, this.options)
  },
}
</script>
