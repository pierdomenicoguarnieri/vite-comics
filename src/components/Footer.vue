<script>
import {menuFooter, menuSocial} from "../data/menus.js";
export default {
  name: "Footer",
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
  .top{
    background-image: url("./src/assets/img/footer-bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    height: 370px;
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
      height: 100%;
      background-image: url("./src/assets/img/dc-logo-bg.png");
      background-repeat: no-repeat;
      background-position: center;
    }
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
            a:hover{
              transition: all .3s;
              filter: brightness(60%);
            }
          }
        }
      }
    }
  }
</style>