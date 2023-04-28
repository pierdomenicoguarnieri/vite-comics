<script>
import {menuCta} from "../../data/menus.js";

export default {
  name: "Cta",
  data(){
    return{
      menuCta
    }
  },
  methods:{
    getImage(img){
      console.log(img);
      return new URL(img, import.meta.url).href;
    }
  }
}
</script>

<template>
  <div class="cta">
      <div class="container">
        <div class="element" v-for="(element, index) in menuCta" :key="index">
          <img :src="getImage(`../../assets/img/${element.img}`)" :alt="element.text">
          <span>{{element.text}}</span>
        </div>
      </div>
    </div>
</template>

<style lang="scss" scoped>
  @use "../../scss/partial/mixin" as *;
  @use "../../scss/partial/variables" as *;
  .cta{
    background-color: $blue;
    padding: 50px 0;
    .container{
      @include container;
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