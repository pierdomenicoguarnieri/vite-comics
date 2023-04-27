<script>
import {menuCta} from "../data/menus.js";

export default {
  name: "Main",
  data(){
    return{
      menuCta
    }
  }
}
</script>

<template>
  <main>
    <div class="content">
      <div class="container">
        <h1>-- Content goes here --</h1>
      </div>
    </div>
    <div class="cta">
      <div class="container">
        <div class="element" v-for="(element, index) in menuCta" :key="index">
          <img :src="element.img" :alt="element.text">
          <span>{{element.text}}</span>
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
  @use "../scss/partial/mixin" as *;
  @use "../scss/partial/variables" as *;
  
  .container{
    @include container;
  }
  .content{
    background-color: $black;
    color: white;
    padding: 50px 0;
  }
  .cta{
    background-color: $blue;
    padding: 50px 0;
    .container{
      @include displayFlex("evenly");
    }
    .element{
      @include displayFlex("vertical");
      span{
        color: $white;
        text-transform: uppercase;
        font-size: $sm-text;
      }
      img{
        height: 50px;
        margin-right: 15px;
      }
      &:last-child{
        img{
          width: 60px;
        }
      }
    }
  }
</style>