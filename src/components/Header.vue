<script>
import {menuTop} from "../data/menus.js";
export default {
  name: "Header",
  data(){
    return{
      menuTop,
      counter: 0
    }
  }
}
</script>

<template>
  <header>
    <div class="container">
      <div class="left">
        <img src="../assets/img/dc-logo.png" alt="">
      </div>
      <div class="right">
        <nav>
          <ul>
            <li v-for="(link, index) in menuTop" :key="index"><a :href="link.href" :class="{active : counter == index}" @click="counter = index">{{link.text}}</a></li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
  @use "../scss/partial/mixin" as *;
  @use "../scss/partial/variables" as *;

  header{
    height: 100px;
    .container{
      height: 100%;
      @include container;
      @include displayFlex("between");
      .left, .right{
        @include displayFlex("vertical");
      }
      img{
        max-height: 80%;
      }
      li{
        display: inline-block;
        a{
          margin: 0 15px;
          color: $grey;
          font-weight: $bold;
          padding-bottom: 34px;
          border-bottom: 5px solid transparent;
          text-transform: uppercase;
          font-size: $s-text;
          &:hover{
            transition: all .3s;
            border-bottom: 5px solid $blue;
            color: $blue;
          }
          &.active{
            border-bottom: 5px solid $blue;
            color: $blue;
          }
        }
      }
    }
  }

</style>