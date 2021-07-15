<template>
  <div class="container-fluid">

    <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#"><h1>Boolflix</h1></a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
        <li class="nav-item">
            <a class="nav-link" href="#">Film</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">Serie TV</a>
        </li>
        <li class="nav-item">
            <a class="nav-link" href="#">Prossimamente</a>
        </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
        <input class="searchbar form-control mr-sm-2" type="search" placeholder="Cerca un film o una serie tv" v-model="textSearch" @keyup="$emit('ricerca', textSearch)">
        </form>
  </div>
    </nav>

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

.searchbar{
    width: 250px;
}

</style>