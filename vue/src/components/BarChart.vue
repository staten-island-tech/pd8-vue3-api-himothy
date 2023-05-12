<script setup>
import { ref, onMounted } from 'vue'
import piechart from '../components/PieChart.vue'
const dataset = ref([])
async function getdata() {
  try {
    const response = await fetch(
      'https://data.cityofnewyork.us/resource/tg4x-b46p.json?$select=eventid,borough,subcategoryname,eventtype'
    )
    const data = await response.json()
    dataset.value = data
    console.log(data)
  } catch (error) {
    console.log(error)
  }
}
onMounted(getdata())
</script>
<template>
  <div class="film-data">
    <h1>Film Data</h1>
    <div class="container">
      <piechart
        v-for="data in dataset"
        :key="data.eventid"
        :id="data.eventid"
        :borough="data.borough"
        :event="data.subcategoryname"
        :eventtype="data.eventtype"
      />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.piechart {
  flex-basis: calc(33.33% - 20px);
  margin-bottom: 20px;
}
</style>
