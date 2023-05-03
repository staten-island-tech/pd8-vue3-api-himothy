<template>
  <div class="container">
    <PokemonCard
      v-for="(monster, index) in pokemon"
      :key="monster.name"
      :id="index + 1"
      :pokemon="monster"
    />
  </div>
</template>

<script setup>
const pokemon = ref('')
async function getPokemon() {
  let res = await fetch('https://pokeapi.co/api/v2/ability/?limit=20&offset=20')
  let data = await res.json()
  pokemon.value = data.results
}
onMounted(() => {
  getPokemon()
})
</script>

<style scoped></style>
