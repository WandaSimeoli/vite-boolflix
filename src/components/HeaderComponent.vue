<script>
import { store } from '../store.js';
export default {
  components :{
  },

  data() {
    return { 
      store
     }
  },
  methods: {
  }
}
</script>

<template>
  <header>
  <input type="text" placeholder="Inserisci il film"
  v-model="store.searchFilm">
  <button @click="$emit('performSearch')">Cerca</button>
  </header>
</template>

<style scoped lang="scss">
</style>