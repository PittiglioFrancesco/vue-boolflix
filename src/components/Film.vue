<template>
  <div class="film">
      <ul>
          <li><img :src="'https://image.tmdb.org/t/p/w342'+info.poster_path" alt=""></li>
          <li><strong>Titolo: </strong> {{info.title || info.name}} </li>
          <li><strong>Titolo originale: </strong> {{info.original_title}} </li>
          <li><strong>Lingua: </strong> <img :src="'@/assets/' + info.original_language + '.png'" :alt="info.original_language"> </li>
          <li><strong>Voto: </strong> {{info.vote_average}} </li>
      </ul>
  </div>
</template>

<script>
export default {

    name: "Film",
    props: ["info"]

}
</script>

<style lang="scss" scoped>

ul {
    margin: 30px 0;
}

</style>