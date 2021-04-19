<script>
import { Line } from 'vue-chartjs'

export default {
  extends: Line,
  computed: {
    chartDataConfig() {
      return {
        labels: [],
        datasets: [
          {
            data: [],
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
  },
}
</script>
