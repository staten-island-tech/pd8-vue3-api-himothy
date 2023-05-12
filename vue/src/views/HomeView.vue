<template>
  <div class="container">
    <PokemonCard
<<<<<<< HEAD
      v-for="(unique_squirrel_id, index) in squirrel"
      :key="unique_squirrel_id"
      :id="index + 1"
      :pokemon="unique_squirrel_id"
=======
      v-for="(monster, index) in pokemon"
      :key="monster.name"
      :id="index + 1"
      :pokemon="monster"
>>>>>>> de0ba53a723be729a5da0818de85f6d871df317b
    />
  </div>
</template>

<script setup>
<<<<<<< HEAD
import { ref, onMounted } from 'vue'
import PokemonCard from '../components/PokemonCard.vue'

const squirrel = ref('')
async function getSquirrel() {
  let res = await fetch('https://data.cityofnewyork.us/resource/vfnx-vebw.json')
=======
const pokemon = ref('')
async function getPokemon() {
  let res = await fetch('https://pokeapi.co/api/v2/ability/?limit=20&offset=20')
>>>>>>> de0ba53a723be729a5da0818de85f6d871df317b
  let data = await res.json()
  squirrel.value = data.results
}
onMounted(() => {
  getSquirrel()
})
</script>

<<<<<<< HEAD
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
=======
<style scoped></style>
>>>>>>> de0ba53a723be729a5da0818de85f6d871df317b
