<template>
  <div id="app">
    <Header @ricerca="ricercaFilm"/>
    <Main :films="arrayFilm" :series="arraySerie" :campoRicerca="searchText" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      apiURLMovie:'https://api.themoviedb.org/3/search/movie?',
      apiURLSerie:'https://api.themoviedb.org/3/search/tv?',
      apiKey:'ee7c70302b256bf9639aba651036d09e',
      language: 'it_IT',
      arrayFilm: [],
      arraySerie: [],
      searchText: ''
    }
  },
  methods:{
    ricercaFilm(testo){
      this.searchText = testo;
      axios
      .get(this.apiURLMovie, {
        params: {
          api_key: this.apiKey,
          language: this.language,
          query: testo
        }
      })
      .then(response =>  {
        this.arrayFilm = response.data.results;
      });

      axios
      .get(this.apiURLSerie, {
        params: {
          api_key: this.apiKey,
          language: this.language,
          query: testo
        }
      })
      .then(response =>  {
        // console.log(response.data.results)
        this.arraySerie = response.data.results;
      });
    }
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>