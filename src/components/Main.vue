<script>
import Cta from "./partials/Cta.vue";
import Card from "./partials/Card.vue";
import cardJson from "../data/json/dc-comics.json";

export default {
  name: "Main",
  components: {
    Cta,
    Card
  },
  data(){
    return{
      cardJson,
    }
  }
}
</script>

<template>
  <main>
    <div class="content">
      <div class="container">
        <span>Current series</span>
        <div class="card-container">
          <Card v-for="(element, index) in cardJson" :key="index" :img="element.thumb" :title="element.series"/>
        </div>
        <button type="button">Load More</button>
      </div>
    </div>
  </main>
  <Cta/>
</template>

<style lang="scss" scoped>
  @use "../scss/partial/mixin" as *;
  @use "../scss/partial/variables" as *;
  
  .container{
    @include container;
    flex-direction: column;
    position: relative;
    text-align: center;
    .card-container{
      width: 100%;
      @include displayFlex(none);
      flex-wrap: wrap;
      text-align: start;
    }
    button{
      padding: 10px 40px;
      border: 2px solid transparent;
      background-color: $blue;
      color: $white;
      text-transform: uppercase;
      font-weight: $bold;
      cursor: pointer;
      &:hover{
        transition: all .3s;
        background-color: transparent;
        border: 2px solid $blue;
      }
    }
  }
  .content{
    background-color: $black;
    color: white;
    padding: 50px 0;
    span{
      position: absolute;
      bottom: 100%;
      left: 0;
      transform: translate(0, -40%);
      padding: 10px 20px;
      text-transform: uppercase;
      font-weight: $extra-bold;
      font-size: $xl-text;
      background-color: $blue;
    }
  }
</style>