<template>
    <section class="products-section">

        <hr>
    
        <div class="products-section__tabs scrollbar">
            <a v-on:click="activetab=1" v-bind:class="[ activetab === 1 ? 'active' : '' ]">POPULAR</a>
            <a v-on:click="activetab=2" v-bind:class="[ activetab === 2 ? 'active' : '' ]">NEW ARRIVALS</a>
            <a v-on:click="activetab=3" v-bind:class="[ activetab === 3 ? 'active' : '' ]">BEST SELLERS</a>
            <a v-on:click="activetab=4" v-bind:class="[ activetab === 4 ? 'active' : '' ]">SPECIAL OFFERS</a>
            <a v-on:click="activetab=5" v-bind:class="[ activetab === 5 ? 'active' : '' ]">COMING SOON</a>
        </div>

        <div class="content">

            <div class="content-container" v-for="data in filter(activetab)" :key="data.productCode" v-bind:class="data.class" @click="goToProduct(data.productCode)">
                <div class="content-container__wrapper">
                    <div class="img-container" v-bind:class="data.class">
                        <img class="product-img" v-bind:src="require('@/assets/' + data.img)" v-bind:alt="data.imgAlt">
                    </div>
                    <div class="product-info">
                        <h5 class="product-info__headline">{{data.productName}}</h5>
                        <p class="product-info__description">{{data.productDescription}}</p>
                        <div class="product-info__buttons-container">
                            <button class="round-icon-button"><i class="round-icon-button__icon fas fa-shopping-cart"></i></button>
                            <button class="round-icon-button"><i class="round-icon-button__icon fas fa-heart"></i></button>
                            <button class="round-icon-button"><i class="round-icon-button__icon fas fa-compress-arrows-alt"></i></button>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    
        <hr>

    </section>
</template>


<script>

export default {
    name: 'Products',

    data: function() {
        return {
            activetab: 1,
            tabs: [
                {
                    id: 1,
                    productCode: 123,
                    img: 'product1.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small',
                    productName: 'Black Long Sleeved Sweatshirt',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 231,
                    img: 'product2.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small',
                    productName: 'Black Long Sleeved Sweatshirt',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                                {
                    id: 1,
                    productCode: 321, 
                    img: 'product3.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'big',
                    productName: 'Black Long Sleeved Sweatshirt',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 345, 
                    img: 'product4.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'big',
                    productName: 'Black Long Sleeved Sweatshirt',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 453, 
                    img: 'product5.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small',
                    productName: 'Black Long Sleeved Sweatshirt',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 543, 
                    img: 'product6.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small',
                    productName: 'Black Long Sleeved Sweatshirt',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
            ],
        }
    },

    methods: {
        filter: function(activetab) {
            return this.tabs.filter(function(tab) {
                return tab.id === activetab
            })
        },

        goToProduct: function(proName) {
            this.$router.push({name:'product',params:{id:proName}})
        }
    }
}
</script>


<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";



  .products-section {
    margin: 50px auto 50px auto;
    @include flexcolumn;
    min-width: $width-medium;
    max-width: $width-big;
    padding: 0px 40px 0px 40px;

    @include media-query(small) {
      min-width: $width-small;
      padding: 0;
    }

      .products-section__tabs {
        margin: 40px 0px 40px 0px;

        @include media-query(small) {
          overflow: hidden;
          overflow-x: scroll;
          padding: 0px 10px 10px 10px;
        }

          & a {
            cursor: pointer;
            padding: 12px 24px;
            white-space: nowrap;

            &:first-child {
              padding-left: 0px;
            }

            &:hover {
              color: $color-cyan;
            }

            &.active {
              color: $color-cyan;
              cursor: default;
            }
        }
    }

    .scrollbar::-webkit-scrollbar-track {
      box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	  -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	  border-radius: 10px;
	  background-color: $color-white;
    }

    .scrollbar::-webkit-scrollbar {
	  width: 12px;
	  background-color: $color-white;
    }

    .scrollbar::-webkit-scrollbar-thumb {
	  border-radius: 10px;
      box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	  -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	  background-color: $color-cyan;
    }

    .content {
      @include grid(20px, 20px, auto);
      margin: 0px 0px 40px 0px;

    .content-container {
      position: relative;
      width: 100%;
      cursor: pointer;

      &:hover {
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
      }

      &:hover .product-info{
        display: flex;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
      }

        .content-container__wrapper {
          position: absolute;
          width: 100%;
        }
    }

    .img-container {
      position: relative;
      @include flexcolumn-cc;
      background-color: $color-lightgrey;
      width: 100%;
    }

      .product-info {
        position: absolute;
        width: 100%;
        display: none;
        background-color: $color-white;
        flex-direction: column;
        align-items: center;
        text-align: center;
        z-index: 999;
        padding: 10px 5px 10px 5px;
        -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
        box-sizing: border-box;

        .product-info__headline {
          color: $color-darkgrey;
          margin-bottom: 5px;
        }   

        .product-info__description {
          font-size: 0.8em;
          color: lighten($color-darkgrey, 30%);
        }

        .product-info__buttons-container {
          width: 120px;
          margin-top: 15px;
          @include flexrow-sb;

          .round-icon-button {
            background-color: $color-darkgrey;
            border: none;
            border-radius: 50%;
            height: 30px;
            width: 30px;
            cursor: pointer;
            color: #ffffff;

            &:hover {
              background-color: $color-cyan;
            }
          }
        }
      }

      .big {
        height: 500px;
        @include grid-item-span(span 2, span 6);

        @include media-query(small) {
          @include grid-item-span(span 2, span 12);
          height: 300px;
          width: 100%;
        }
      }

      .small {
        height: 300px;
        @include grid-item-span(span 1, span 3);

        @include media-query(small) {
          @include grid-item-span(span 1, span 12);
          height: 300px;
          width: 100%;
        }
      }

      .product-img {
        height: 100%;
        object-fit: cover;

        @include media-query(small) {
          width: 100%;
        }
      }
    }
  }

</style>
