<template>
  <div class="film">
      <ul>
          <li><img :src="'https://image.tmdb.org/t/p/w342'+info.poster_path" alt=""></li>
          <li><strong>Titolo: </strong> {{info.title || info.name}} </li>
          <li><strong>Titolo originale: </strong> {{info.original_title}} </li>
          <li><strong>Lingua: </strong><img :src="'../assets/img/' + info.original_language + '.png'" :alt="info.original_language"></li>
          <li><strong>Voto:
            </strong> {{info.vote_average}}
            <span v-if="info.vote_average == 10">
                <i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i>
            </span>
            <span v-if="(info.vote_average > 8 && info.vote_average < 10)">
                <i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="gray fas fa-star"></i>
            </span>
            <span v-if="(info.vote_average > 6 && info.vote_average < 8)">
                <i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i>
            </span>
            <span v-if="(info.vote_average > 4 && info.vote_average < 6)">
                <i class="yellow fas fa-star"></i><i class="yellow fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i>
            </span>
            <span v-if="(info.vote_average > 2 && info.vote_average < 4)">
                <i class="yellow fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i>
            </span>
            <span v-if="(info.vote_average == 0)">
                <i class="gray fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i><i class="gray fas fa-star"></i>
            </span>
           </li>
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

.gray{
    color: gray;
  }

  .yellow{
    color: gold;
  }

</style>