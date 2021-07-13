<template>
  <div class="film">
      <ul>
          <li><strong>Titolo: </strong> {{info.title}} </li>          <li><strong>Titolo: </strong> {{info.title}} </li>
          <li><strong>Titolo originale: </strong> {{info.original_title}} </li>
          <li><strong>Lingua: </strong> {{info.original_language}} </li>
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