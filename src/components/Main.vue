<script>
import Cta from "./partials/Cta.vue";

export default {
  name: "Main",
  components: {
    Cta
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
  </main>
  <Cta/>
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
</style>