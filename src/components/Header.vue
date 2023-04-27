<script>
export default {
  name: "Header"
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
            <li><a href="">Link</a></li>
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
          text-decoration: none;
          color: $grey;
          font-weight: $bold;
          padding-bottom: 35px;
          border-bottom: 3px solid transparent;
          &:hover{
            transition: all .3s;
            border-bottom: 3px solid $blue;
            color: $blue;
          }
        }
      }
    }
  }

</style>