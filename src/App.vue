<script>
// my-component.js
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import axios from 'axios';


export default {
  components :{
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },

  data() {
    return {   
    searchFilm :'',
    films : []
  };
  },
  methods: {
    search() {
      axios
      .get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'a7519aa2a486095820e427650422a38e',
          query: this.searchFilm
        }
      })
      .then (res => {
        console.log(res);

        this.films = this.data.results;
        
      });
    } 
  },
};
</script>

<template>
    <header>
  <input type="text" placeholder="Inserisci il film"
  v-model="searchFilm">
  <button @click="search()">Cerca</button>
  </header>
  <main>
    {{ films }}
  </main>
  <!-- <HeaderComponent />
  <MainComponent />
  <FooterComponent /> -->
</template>

<style lang="scss">
@use "assets/scss/main.scss";
</style>
