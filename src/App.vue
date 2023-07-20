<script>
// my-component.js
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import axios from 'axios';
import { store } from './store.js';

export default {
  components :{
    HeaderComponent,
    MainComponent,
    FooterComponent,
  },

  data() {
    return {  
      store 
  };
  },
  methods: {
    search() {
            axios.get('https://api.themoviedb.org/3/search/movie', {
              params: {
                api_key: 'a7519aa2a486095820e427650422a38e',
                query: this.store.searchFilm
              }
            })
            .then((response) => {
              console.log(response);
              this.store.films = response.data.results;
            });
        }
    },
  };
</script>

<template>
   
  <HeaderComponent @performSearch="search()"/>
  <MainComponent />
  <FooterComponent />
</template>

<style lang="scss">
@use "assets/scss/main.scss";
</style>
