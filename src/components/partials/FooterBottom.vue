<script>
import {menuSocial} from "../../data/menus.js";
export default {
  name: "FooterBottom",
  data(){
    return{
      menuSocial
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
  <div class="bottom">
    <div class="container">
      <div class="left">
        <span>Sing-up now!</span>
      </div>
      <div class="right">
        <span>Follow us</span>
        <nav>
          <ul>
            <li v-for="(icon, index) in menuSocial" :key="index">
              <a :href="icon.href"><img :src="getImage(`../../assets/img/${icon.img}`)" alt=""></a>
            </li>
          </ul>
        </nav>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
  @use "../../scss/partial/mixin" as *;
  @use "../../scss/partial/variables" as *;

  .container{
    @include container;
    @include displayFlex("between");
    height: 100%;
  }
  .bottom{
    background-color: $grey;
    padding: 30px 0;
    @include displayFlex("both");
    .left{
      @include displayFlex("vertical");
      span{
        padding: 10px 10px;
        border: 2px solid $blue;
        color: $white;
        text-transform: uppercase;
      }
    }
    .right{
      @include displayFlex("vertical");
      span{
        color: $blue;
        font-size: $xl-text;
        text-transform: uppercase;
        font-weight: $bold;
      }
      nav{
        height: 100%;
        @include displayFlex("vertical");
        ul{
          margin-left: 25px;
        @include displayFlex("none");
          li:not(:last-child){
            margin-right: 15px;
          }
          a:hover{
            transition: all .3s;
            filter: brightness(60%);
          }
        }
      }
    }
  }
</style>