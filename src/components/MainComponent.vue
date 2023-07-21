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
    flags(lang) {
      if (lang == 'it') {
        return 'https://img.icons8.com/?size=512&id=PW8KZnP7qXzO&format=png'
      } else if (lang == 'en') {
        return 'https://img.icons8.com/?size=1x&id=t3NE3BsOAQwq&format=png'
      } else if (lang == 'ja') {
        return 'https://img.icons8.com/?size=512&id=McQbrq9qaQye&format=png'
      } else if (lang == 'es') {
        return 'https://img.icons8.com/?size=512&id=MRQWA3gxIrCt&format=png'
      } else if (lang == 'fr') {
        return 'https://img.icons8.com/?size=512&id=3muzEmi4dpD5&format=png'
      } else if (lang == 'de') {
        return 'https://img.icons8.com/?size=512&id=hTMPE6ntTofO&format=png'
      } 
      else {
        return 'https://img.icons8.com/?size=512&id=39590&format=png'
      }
    },
    vote(element) {
      return Math.ceil(element / 2);
    }
  }
}
</script>

<template>
<main>
  <h2>Films</h2>
    <ul>
      <li v-for="(singleFilm, i) in store.films" :key='i'>
        <ol>
          <li> Titolo: {{ singleFilm.title }}</li>
          <li>  <img :src="'https://image.tmdb.org/t/p/w500'+ singleFilm.poster_path" alt="Poster not available" class="w-25"></li>
          <li> Titolo originale: {{ singleFilm.original_title }}</li>
          <li class="text-uppercase"> 
            <img :src="flags(singleFilm.original_language)" alt="">
            Lingua originale:{{ singleFilm.original_language }}</li>
          <li> Votazione: <span v-for="number in vote(singleFilm.vote_average)" :key="number">	★ </span>
            <span v-for="number in (5 - vote(singleFilm.vote_average))" :key="number">	☆ </span></li>
        </ol>
      </li>
    </ul>
    <h2>Series TV</h2>
    <ul>
      <li v-for="(singleSeries, i) in store.seriesTv" :key='i'>
        <ol>
          <li> Titolo:{{ singleSeries.name }}</li>
          <li>  <img :src="'https://image.tmdb.org/t/p/w500'+ singleSeries.poster_path" alt="Poster not available"></li>
          <li> Titolo originale:{{ singleSeries.original_name }}</li>
          <li class="text-uppercase"> 
            <img :src="flags(singleSeries.original_language)" alt="">
            Lingua originale: {{ singleSeries.original_language }}</li>
          <li> Votazione: {{ singleSeries.vote_average }}</li>
        </ol>
      </li>
    </ul>
  </main>
</template>

<style scoped lang="scss">
img {
  width: 25px;
}
</style>