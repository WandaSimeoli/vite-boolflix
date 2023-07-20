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
  methods: {}
}
</script>

<template>
<main>
    <ul>
      <li v-for="(singleFilm, i) in store.films" :key='i'>
        <ol>
          <li> {{ singleFilm.title }}</li>
          <li> {{ singleFilm.original_title }}</li>
          <li> {{ singleFilm.original_language }}</li>
          <li> {{ singleFilm.vote_average }}</li>
        </ol>
      </li>
    </ul>
  </main>
</template>

<style scoped lang="scss">
</style>