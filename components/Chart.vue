<script>
import { Line } from 'vue-chartjs'

export default {
  extends: Line,
  props: {
    yearValue: Array,
    require: true,
  },
  computed: {
    chartDataConfig() {
      const array =  this.yearValue;

      const labels = array.map(e=>e.label)
      const data = array.map(e=>e.value)
      return {
        labels,
        datasets: [
          {
            data,
          },
        ],
      }
    },
    options() {
      return {}
    },
  },
  mounted() {
    this.renderChart(this.chartDataConfig, this.options)
  }
}
</script>
