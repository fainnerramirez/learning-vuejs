
<script setup>
import { ref } from 'vue'

const characters = ref([])

const getCharacters = async () => {
  const response = await fetch("https://rickandmortyapi.com/api/character");
  const { results } = await response.json();
  characters.value = results;
}

getCharacters();
</script>

<template>
    <div v-for="character in characters" class="card"  style="width: 18rem; margin: 10px;">
        <img :src="character.image" class="card-img-top" alt="character.name">
        <div class="card-body">
            <p class="card-text">
                {{ character.name }} - {{ character.species }}
            </p>
        </div>
    </div>
</template>