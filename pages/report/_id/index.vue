<template>
  <div>
    <h1>Report</h1>
  </div>
</template>

<script>
/*
  Instructions:
  - Using axios get data from /api/id.json substiting 'id' with the the final param in the route
  - For testing purposes use http://localhost:3000/report/1
  - Transform the response to an array of objects e.g. [ { label: 2016, value: 0 }, { label: 2017, value: 4  }, etc]
  - Add the component 'Chart' to the page and pass int the array of objects as a param
  - Update header to include the report id e.g. "Report 1"
  - Update the page layout so that on
    - desktop: layout is 2 columns with Header in left column and Chart in right column
    - mobile: layout is 1 column with Header appearing above Chart
*/

export default {
  name: 'Report',
  async asyncData({ $axios, params }) {
    return {}
  },
}
</script>
