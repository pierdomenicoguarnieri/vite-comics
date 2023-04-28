<script>
import FooterTop from "./partials/FooterTop.vue";
import FooterBottom from "./partials/FooterBottom.vue";
import {menuFooter, menuSocial} from "../data/menus.js";
export default {
  name: "Footer",
  components:{
    FooterTop,
    FooterBottom
  }
}
</script>

<template>
  <footer>
    <FooterTop/>
    <FooterBottom/>
  </footer>
</template>

<style>

</style>