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
  <header class=" text-bg-dark d-flex align-items-center justify-content-between p-4">
    <img src="../assets/img/logo.png" alt="Logo Boolflix" class="text-bg-dark rounded">
    <div class="input-group mb-3 w-25 m-3">
      <input type="text" placeholder="Inserisci il film" class="form-control " aria-describedby="button-addon2"
  v-model="store.searchFilm">
  <button @click="$emit('performSearch')" type="button" class="btn btn-outline-light" id="button-addon2">Cerca</button>
    </div>
 
  </header>
</template>

<style scoped lang="scss">
img {
  width: 20%;
}
input {
  height: 40px;
}
</style>
