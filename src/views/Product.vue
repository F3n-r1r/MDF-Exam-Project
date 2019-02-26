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

    .product-section {
        margin: 50px auto 100px auto;
        width: 1024px;
        display: grid;
        grid-row-gap: 30px;
        grid-column-gap: 30px;
        grid-template-columns: repeat(12, 1fr);
        grid-auto-rows: auto;

        @media only screen and (min-width : 320px) and (max-width : 480px) { //480
            max-width: 320px;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 0px 10px 0px 10px;
        }

        .productInfo {
          width: 100%;
        }
    }
    
</style>
