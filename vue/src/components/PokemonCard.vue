<template>
  <div class="card">
    <h2>
      {{ unique_squirrel_id }}
    </h2>
    <h3>
      {{ id }}
    </h3>
  </div>
</template>

<script setup>
const props = defineProps({
  squirrel: Object,
  id: Number
})
</script>

<style scoped>
.card {
  width: 28%;
  height: 500px;
  background-color: aliceblue;
  margin: 30px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 10px;
  text-transform: uppercase;
}
</style>
