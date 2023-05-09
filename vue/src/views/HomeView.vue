<template>
  <div class="container">
    <PokemonCard
      v-for="(unique_squirrel_id, index) in squirrel"
      :key="unique_squirrel_id"
      :id="index + 1"
      :pokemon="unique_squirrel_id"
    />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import PokemonCard from '../components/PokemonCard.vue'

const squirrel = ref('')
async function getSquirrel() {
  let res = await fetch('https://data.cityofnewyork.us/resource/vfnx-vebw.json')
  let data = await res.json()
  squirrel.value = data.results
}
onMounted(() => {
  getSquirrel()
})
</script>

.
<style scoped>
.container {
  width: 80vw;
  margin: 30px auto;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
}
</style>
