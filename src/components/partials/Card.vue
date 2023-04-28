<script>
export default {
  name: "Card",
  props:{
    img: String,
    title: String
  }
}
</script>

<template>
  <div class="card">
    <div class="img-container">
      <img :src="img" alt="">
    </div>
    <span>{{title}}</span>
  </div>
</template>

<style lang="scss" scoped>
  @use "../../scss/partial/variables" as *;
  .card{
    width: calc(100%/6);
    margin-bottom: 30px;
    padding: 0 10px;
    &:hover{
      cursor: pointer;
      img{
        transition: all .3s;
        filter: brightness(50%);
      }
      span{
        transition: all .3s;
        color: $blue;
      }
    }
    .img-container{
      width: 100%;
      aspect-ratio: 2/3;
      margin-bottom: 5px;
      img{
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    span{
      text-transform: uppercase;
      font-weight: $semi-bold;
    }
  }
</style>