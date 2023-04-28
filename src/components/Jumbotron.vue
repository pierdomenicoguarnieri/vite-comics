<script>
export default {
  name: "Jumbotron"
}
</script>

<template>
  <div class="jumbotron">
    <img src="@/assets/img/jumbotron.jpg" alt="">
  </div>
</template>

<style lang="scss" scoped>
  .jumbotron{
    height: 400px;
    overflow: hidden;
    img{
      display: block;
    }
  }
</style>