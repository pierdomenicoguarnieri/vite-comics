<script>
import FooterTop from "./partials/FooterTop.vue";
import {menuFooter, menuSocial} from "../data/menus.js";
export default {
  name: "Footer",
  components:{
    FooterTop
  },
  data(){
    return{
      menuFooter,
      menuSocial
    }
  }
}
</script>

<template>
  <footer>
    <FooterTop/>
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
                <a :href="icon.href"><img :src="icon.img" alt=""></a>
              </li>
            </ul>
          </nav>
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
  @use "../scss/partial/mixin" as *;
  @use "../scss/partial/variables" as *;

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
        @include displayFlex("vertical");
        height: 100%;
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