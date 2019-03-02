<template>
  <div class="home">

    <section class="banner">
      <div class="wrapper">
        <h1 class="companyLogo"><span>A</span><span>V</span><span>E</span></h1>
        <button class="primary-btn">SHOP MEN'S COLLECTION</button>
      </div>    
    </section>

    <Products />

    <Lookbook />

  </div>
</template>

<script>
import Lookbook from '@/components/home-components/Lookbook.vue'
import Products from '@/components/home-components/Products.vue'

export default {
    components: {
      Lookbook,
      Products
  }
}
</script>


<style scoped lang="scss">

  @import "../styles/utilities/mixins.scss";
  @import "../styles/utilities/vars.scss";

  .banner {
    height: 920px;
    background-color: $color-lightgrey;;
    @include flexrow-cc;
    min-width: $width-medium;

    @include media-query(small) {
        height: 460px;
        min-width: $width-small;
    }

      .wrapper {
        position: relative;
        @include background-image("../assets/bgImgHomeLarge.png", left);
        width: $width-big;
        height: 100%;
        @include flexrow-cc;
        padding: 0px 50px 0px 50px;
        
        @include media-query(small) {
          @include background-image("../assets/bgImgHomeSmall.png", center);
        }

          .companyLogo {
            font-size: 20em;
            color: $color-darkgrey;
            @include flexrow-sb;
            width: 100%;

            @include media-query(small) {
              font-size: 5em;
            }
          }

          .primary-btn {
            position: absolute;
            right: 25px;
            bottom: 150px;
            align-self: flex-end;
            @include primary-button;

            @include media-query(small) {
              bottom: 20px;
            }
          }
      }
  }

</style>
