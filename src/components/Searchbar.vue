<template>
  <div class="container">
      <div class="row">
          <input type="text" placeholder="Cerca un film o una serie tv">
          <button>Reset</button>
          <button>Cerca</button>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

div{
    div{
        display: flex;
        width: 100%;
        justify-content: center;
        input{
            width: 70%;
        }
        button{
            width: 10%;
        }
    }
}

</style>