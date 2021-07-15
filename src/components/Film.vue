<template>
  <div class="film" :style="{backgroundImage:`url(${image})`}">

    <div class="info">
    <p class="hide"><strong>Titolo: </strong> {{info.title || info.name}}</p>
    <p class="hide"><strong>Titolo originale: </strong> {{info.original_title}}</p> 
    <p class="hide"><strong>Lingua: </strong><img :src="'../assets/img/' + info.original_language + '.png'" :alt="info.original_language"></p>
    <br>
    <p class="hide">
        <strong>Voto: </strong>
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
        {{info.vote_average}}
    </p>
    <p class="hide"><strong>Trama: </strong> {{info.overview}}</p> 
    </div>
           
  </div>
</template>

<script>
export default {

    name: "Film",
    props: ["info"],
    data(){
        return{
            image: 'https://image.tmdb.org/t/p/w342' + this.info.poster_path
        }
    }

}
</script>

<style lang="scss" scoped>

.gray{
    color: gray;
  }

  .yellow{
    color: gold;
  }

  .info{
    width: 342px;
    height: 513px;
    padding: 10px;
    color: white;
    overflow-y: auto;
  }

  .info:hover{
    background-color: rgba($color: #000000, $alpha: 0.5);
  }

  .hide{
      display: none;
  }
  .info:hover .hide{
      display: inline-block;
  }

  .film{
      margin: 40px;
      padding: 0;
      background-image: url('https://image.tmdb.org/t/p/w342 + info.poster_path');
      width: 342px;
      height: 513px;
  }


</style>