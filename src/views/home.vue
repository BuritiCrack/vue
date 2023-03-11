<!-- Home -->

<template>
  <div>
    home
  </div>

</template>

<script>
import { ref } from 'vue';
async function getCharacters() {
  const response = await fetch('https://rickandmortyapi.com/api/character');
  const data = await response.json();
  return data.results;
}
  export default {
    name: 'HomeView',
  setup() {
    const characters = ref([]);

    return {
      characters,
    };
  },
  async created() {
    this.characters = await getCharacters();
  },
};
</script>