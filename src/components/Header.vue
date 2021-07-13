<template>
  <div class="container">

    <div class="row">
        <h1 class="text-center my-5">Boolzapp</h1>
    </div>

    <div class="row">
        <button>Reset</button>
        <input type="text" placeholder="Cerca un film o una serie tv" v-model="textSearch" @keyup="$emit('ricerca', textSearch)">
        <button>Cerca</button>
    </div>

  </div>
</template>

<script>
export default {

    name: "Header",
    data(){
        return{
            textSearch: ''
        }
    }

}
</script>

<style lang="scss" scoped>

.container{
    .row{
        input{
            width: 80%;
        }
        button{
            width: 10%;
        }
    }
}

</style>