<script>
import {menuFooter} from "../../data/menus.js";
export default {
  name: "MenuTop",
  data(){
    return{
      menuFooter
    }
  }
}
</script>

<template>
  <div class="top">
    <div class="container">
      <div class="left">
        <div class="col">
          <h4>dc comics</h4>
          <nav>
            <ul>
              <li v-for="(element, index) in menuFooter.dcComic" :key="index">
                <a href="">{{element.text}}</a>
              </li>
            </ul>
          </nav>
          <h4>shop</h4>
          <nav>
            <ul>
              <li v-for="(element, index) in menuFooter.shop" :key="index">
                <a href="">{{element.text}}</a>
              </li>
            </ul>
          </nav>
        </div>
        <div class="col">
          <h4>dc</h4>
          <nav>
            <ul>
              <li v-for="(element, index) in menuFooter.dc" :key="index">
                <a href="">{{element.text}}</a>
              </li>
            </ul>
          </nav>
        </div>
        <div class="col">
          <h4>sites</h4>
          <nav>
            <ul>
              <li v-for="(element, index) in menuFooter.sites" :key="index">
                <a href="">{{element.text}}</a>
              </li>
            </ul>
          </nav>
        </div>
      </div>
      <div class="right">
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
  }
  .top{
    background-image: url("./src/assets/img/footer-bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    min-height: 370px;
    overflow: hidden;
    h4{
      color: $white;
      text-transform: uppercase;
      font-weight: $bold;
    }
    .left{
      @include displayFlex("none");
      .col{
        padding: 40px 0;
        &:not(:last-child){
          margin-right: 20px;
        }
        ul{
          padding: 10px 0;
        }
        a{
          color: darken($white, 45%);
          text-transform: capitalize;
          font-size: $s-text;
          transition: all .3s;
          &:hover{
            text-decoration: underline;
            color: darken($white, 35%);
          }
        }
      }
    }
    .right{
      width: 50%;
      background-image: url("./src/assets/img/dc-logo-bg.png");
      background-repeat: no-repeat;
      background-position: center;
    }
  }
</style>