<template>
  <div class="container">

      <div class="row">

        <p>Risultati per {{campoRicerca}}: </p>

        <div class="row">
            <h3>Films: </h3>
        </div>

        <Film v-for="film in films" :key="film.id" :info="film"/>

        <div class="row">
            <h3>Serie TV: </h3>
        </div>

        <Serie />
        
      </div>
      
  </div>
</template>

<script>

import Film from '@/components/Film.vue'
import Serie from '@/components/Serie.vue'

export default {

    name: "Searchbar",
    components: {
        Film,
        Serie
    },
    props: {
        films: Array,
        campoRicerca: String
    }

};

</script>

<style lang="scss" scoped>

</style>