<script setup>
import { ref } from 'vue'
import CardPersonaje from './CardPersonaje.vue';

const characters = ref([])

const getCharacters = async () => {
  const response = await fetch("https://rickandmortyapi.com/api/character");
  const { results } = await response.json();
  characters.value = results;
  console.log(characters.value);
}

getCharacters();
</script>

<template>
  <div v-for="character in characters" class="container">
    <CardPersonaje 
      :name="character.name" 
      :image="character.image" 
      :species="character.species"/>
  </div>
</template>

<style scoped>
.container {
  background-color: brown;
  width: 1200px;
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
}
</style>