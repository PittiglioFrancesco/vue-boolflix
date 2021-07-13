<template>
  <div id="app">
    <Header @ricerca="ricercaFilm"/>
    <Main :films="arrayFilm" :campoRicerca="searchText" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from 'axios'


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
       apiURL:'https://api.themoviedb.org/3/search/movie?api_key=ee7c70302b256bf9639aba651036d09e&query=matrix',
       apiKey:'ee7c70302b256bf9639aba651036d09e',
       language: 'it_IT',
       arrayFilm: [],
       searchText: ''
    }
  },
  methods:{
    ricercaFilm(testo){
      this.searchText = testo;
      axios
      .get(this.apiURL, {
        params: {
          api_key: this.apiKey,
          language: this.language,
          query: testo
        }
      })
      .then(response =>  {
        console.log(response.data.results)
        this.arrayFilm = response.data.results;
      });
      console.log(testo);
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
