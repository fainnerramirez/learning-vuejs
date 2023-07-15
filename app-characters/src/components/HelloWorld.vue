<script setup>
import { ref } from 'vue'

const characters = ref([])

const getCharacters = async () =>  {
  const response = await fetch("https://rickandmortyapi.com/api/character");
  const { results } = await response.json();
  characters.value = results;
}

getCharacters();
</script>

<template>
  <div class="container">
      <div v-for="data in characters" :key="data.id" class="square">
          <img :src="data.image"/>
          <h4>{{ data.name }} - {{ data.species }}</h4>
      </div>
  </div>
</template>
 
<style scoped>
  .container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }
  .square {
    border: 5px solid #000000;

  }
</style>