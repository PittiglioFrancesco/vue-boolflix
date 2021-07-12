<template>
  <div id="app">
    <Header/>
    <Searchbar/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Searchbar from './components/Searchbar.vue'

export default {
  name: 'App',
  components: {
    Header,
    Searchbar
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
