<template>
  <div class="display">
    <h1>Report</h1>
    <div class="chart-example">
      <h2>Preview</h2>
      <Chart :yearValue="yearValue" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Report',
  async asyncData({ $axios, params }) {
    const { id } = params;
    try {
      const { data } = await $axios.get(`https://allansolutions.com/.netlify/functions/interview-fullstack-${id}`);
      const arrayYears = [];
      for (let e in data) {
        const year = e.split('.')[1]
        const value = data[`year.${year}`]
        const response = {
          label: year,
          value,
        }
        arrayYears.push(response)
      }

      return {
        yearValue: arrayYears,
      }
    } catch (error) {
      throw new error('something is wrong')
    }
  }
}
</script>
<style >
@media only screen and (min-width: 1440px) {
  .display {
    flex-direction: row!important;;
  }
}

.display {
  display: flex;
  flex-direction: column;
}
.chart-example{
  background: hsl(0deg 0% 0% / 50%) ;
  position: relative;
}

.chart-example h2{
  position: absolute;
  top: 50%;
  right: 50%;
}
</style>

<!-- - Place a div on top of the chart that:
    - covers the chart completely
    - has color black and transparency 50%
    - contains the text "Preview" centered both horizontally and vertically -->