<template>
  <div class="product">

    <Header v-bind:HeadlineOne="TitleOne" v-bind:HeadlineTwo="TitleTwo"/>

    <section class="product-section">

        <ProductImgSlider class="productSlider"/>

        <ProductInfo class="productInfo"/>

        <ProductTabs class="productTab"/>

    </section>

  </div>
</template>


<script>
import Header from '@/components/globals/Header.vue'
import ProductInfo from '@/components/product-components/ProductInfo.vue'
import ProductTabs from '@/components/product-components/ProductTabs.vue'
import ProductImgSlider from '@/components/product-components/ProductImgSlider.vue'

export default {
  components: {
    Header,
    ProductInfo,
    ProductTabs,
    ProductImgSlider
  },

  data: function() {
    return {
      TitleOne: 'PRODUCT VIEW',
      TitleTwo: 'GET THIS DYNAMICALLY',
    }
  }
}
</script>


<style scoped lang="scss">

  @import "../styles/utilities/mixins.scss";
  @import "../styles/utilities/vars.scss";

  .product-section {
      margin: 50px auto 100px auto;
      width: $width-medium;
      @include grid(30px, 30px, auto);

      @include media-query(small) {
        max-width: $width-small;
        @include flexcolumn-cv;
      }
  }
    
</style>
