<template>
    <div class="info-container">

        <div class="info-content-container">

            <h3>{{ activeProduct[0].productName }}</h3>

            <div class="info-container__social">

                <div class="reviews">

                    <div class="reviews__stars">
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                        <i class="fas fa-star"></i>
                    </div>

                    <p class="social-text link">
                        3 Reviews(s)
                    </p>

                    <div class="vl"></div>

                    <p class="social-text link">
                        Add a review
                    </p>

                    <div class="vl"></div>

                </div>


                <div class="share">

                    <p class="social-text">
                        Share:
                    </p>

                    <div class="share__icons">
                        <i class="icon fab fa-facebook-f"></i>
                        <i class="icon fab fa-twitter"></i>
                        <i class="icon fab fa-google-plus-g"></i>
                        <i class="icon fab fa-pinterest-p"></i>
                        <i class="icon fab fa-instagram"></i>
                        <i class="icon far fa-envelope"></i>
                    </div>

                </div>

            </div>

            <div class="info-container__pricing">

                <p class="price price--line">
                    107
                </p>

                <p class="price">
                    89.99
                </p>

            </div>

            <div class="info-container__notes">

                <p class="text">
                    AVAILABILITY: <span class="text__value">In stock</span>
                </p>
                <p class="text">
                    PRODUCT CODE: <span class="text__value">#499577</span>
                </p>
                <p class="text">
                    TAGS: <span class="text__value text__value--green">Classic, Casual, V-neck, Loose</span>
                </p>

            </div>

            <div class="info-container__description">

                <p class="text">
                    Donec sem lorem laoreet tempor un risus vitae, rutrum sodales nibh suspendisse est congue metus nunc, id viverra elit loreti rhoncus quis consecteur es. Donec pulvinar tempor lorem a pretium justo interdum.
                </p>
                <ul class="highlighted-list">
                    <li class="highlighted-list__item">
                        Elasticated cuffs
                    </li>
                    <li class="highlighted-list__item">
                        Casual fit
                    </li>
                    <li class="highlighted-list__item">
                        100% Cotton
                    </li>
                    <li class="highlighted-list__item">
                        Free shipping with 4 days delivery
                    </li>
                </ul>
                
            </div>

            <div class="info-container__selection">

                <div class="option-container">
                    <label class="selector-label" for="color">COLOUR</label>
                    <select class="selector-drpdown" name="color" id="color">
                        <option value="" disabled selected>Select Colour</option>
                        <option value="Black">Black</option>
                        <option value="Grey">Grey</option>
                        <option value="Brown">Brown</option>
                    </select>
                </div>

                <div class="option-container">
                    <label class="selector-label" for="size">SIZE</label>
                    <select class="selector-drpdown" name="size" id="size">
                        <option value="" disabled selected>Select Size</option>
                        <option value="Black">Small</option>
                        <option value="Grey">Medium</option>
                        <option value="Brown">Large</option>
                    </select>
                </div>

                <div class="option-container">
                    <label class="selector-label" for="qty">QTY</label>
                    <div class="qty-container">
                        <input class="selector-qty" type="number" v-bind:value="qtyValue" name="qty" id="qty">
                        <div class="spin-container">
                            <button v-on:click="qtyValue += 1" class="spin spin__up"><i class="fas fa-angle-up"></i></button>
                            <button v-on:click="qtyValue -= 1" class="spin spin__down"><i class="fas fa-angle-down"></i></button>
                        </div>
                    </div>
                </div>

            </div>

            <div class="add-button-container">
                <button class="btn"><i class="icon fas fa-shopping-cart"></i>ADD TO CARD</button>
                <button class="btn"><i class="icon far fa-heart"></i>ADD TO LOOKBOOK</button>
                <button class="btn btn--no-border"><i class="icon fas fa-compress-arrows-alt"></i>ADD TO COMPARE</button>
            </div>

        </div>

    </div>

</template>


<script>

export default {
    name: 'ProductInfo',

    data: function() {
        return {
            qtyValue: 1,
            currentProductCode: this.$route.params.id,
            activeProduct: [],
            products: [
                {
                    id: 1,
                    productCode: 123,
                    img: 'product1.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt 1',
                    class: 'small',
                    productName: 'AVE CLASSIC SWEATSHIRT',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 231,
                    img: 'product2.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small',
                    productName: 'Black Long Sleeved Sweatshirt 2',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                                {
                    id: 1,
                    productCode: 321, 
                    img: 'product3.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'big',
                    productName: 'Black Long Sleeved Sweatshirt 3',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 345, 
                    img: 'product4.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt 4',
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
                    productName: 'Black Long Sleeved Sweatshirt 5',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
                {
                    id: 1,
                    productCode: 543, 
                    img: 'product6.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small',
                    productName: 'Black Long Sleeved Sweatshirt 6',
                    productDescription: 'Classic casual long sleeved shirt for men on the move. 100% cotton.'
                },
            ],
        }
    },

   methods: {
        filter: function() {
            var pCode = this.currentProductCode;
            var allProducts = this.products
            var currentProduct = this.activeProduct;

            allProducts = this.products.filter(function(item) {
                return item.productCode == pCode;
            })
            allProducts.forEach(element => {
                currentProduct.push(element)
            });

            return currentProduct;   
        }
    },

    created(){
        this.filter()
    }
}
</script>


<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";

  .info-container {
    @include flexcolumn-sb;
    grid-column: span 6;
    white-space: nowrap;
    font-size: 0.8em;

    @include media-query(small) {
      margin-top: 15px;
    }

      .info-content-container {
        padding: 0px 10px 0px 10px;

        .social-text {
          margin: 0px 10px 0px 10px;
        }

        .info-container__social {
          display: flex;
          margin: 15px 0px 15px 0px;

          @include media-query(small) {
            flex-wrap: wrap;
          }

            .reviews {
              @include flexrow-sbcv;
              width: 100%;

              @include media-query(small) {
                justify-content: start;
              }

                .vl {
                  border-left: 1px solid $color-darkgrey;
                  height: 100%;

                  &:last-child {
                    @include media-query(small) {
                      display: none;
                    }
                  }
                }

                .reviews__stars {
                  color: $color-yellow;

                  :last-child {
                      color: lighten($color-darkgrey, 45%);
                    }
                }

                .link {
                  cursor: pointer;

                  &:hover {
                    color: $color-cyan;
                  }
                }
            }

            .share {
              @include flexrow-sbcv;
              width: 100%;
              
              @include media-query(small) {
                display: none;
              }

                .social-text {
                  margin: 0px 10px 0px 10px;

                    @include media-query(small) {
                      margin: 0px 10px 0px 0px;
                    }
                }

                .share__icons {
                  @include flexrow-sb;
                  width: 100%;

                  @include media-query(small) {
                    justify-content: start;
                  }

                    .icon {
                      color: lighten($color-darkgrey, 40%);
                      cursor: pointer;

                      @include media-query(small) {
                        margin-right: 10px;
                      }

                      &:hover {
                        color: $color-cyan;
                      }
                    }
                }
            }
        }

        .info-container__pricing {
          display: flex;

          .price {
            margin-right: 15px;
            font-size: 2em;
            color: lighten($color-darkgrey, 40%);

              &:before {
                content: "\00a3";
                font-size: 0.6em;
                vertical-align: top;       
              }
            }

            .price--line {
              text-decoration: line-through;
            }
        }

        .info-container__notes {
          margin: 15px 0px 15px 0px;

          .text {
            font-weight: bold;
            margin-top: 15px;

            .text__value {
              font-weight: normal;
            }

              .text__value--green {
                color: $color-cyan;
              }
          }
        }

        .info-container__description {
          color: lighten($color-darkgrey, 40%);
          margin-bottom: 30px;

          .text {
            white-space: pre-line;
            line-height: 1.6;
          }

            .highlighted-list {
              list-style-position: inside;
              line-height: 1.6;
              margin-top: 10px;
            }
        }

        .info-container__selection {
          display: flex;
          margin-bottom: 30px;
        
          @include media-query(small) {
            flex-wrap: wrap;
          }

            .option-container {
              @include flexcolumn;
              position: relative;

              &:last-child {
                @include media-query(small) {
                  margin-top: 15px;
                }
              }

              .selector-label {
                margin-bottom: 5px;
                font-family: $font-sec;
                font-weight: bold;
                color: $color-darkgrey;
                }

              .selector-drpdown {
                padding: 10px;
                margin-right: 25px;
                font-family: $font-main;
                color: lighten($color-darkgrey, 20%);
                border-color: lighten($color-darkgrey, 60%);

                &:focus {
                  outline: none;
                }
              }

              .selector-qty {
                padding: 11px;
                width: 50px;
                font-family: $font-main;
                color: lighten($color-darkgrey, 20%);
                border:1px solid lighten($color-darkgrey, 60%);
                -webkit-appearance: textfield;
                -moz-appearance: textfield;
                appearance: textfield;

                &:focus {
                  outline: none;
                }

                &::-webkit-inner-spin-button, &::-webkit-outer-spin-button {
                  -webkit-appearance: none; 
                  margin: 0;
                }     
              }

              .qty-container {
                position: relative;

                .spin-container {
                  position: absolute;
                  top: 1px;
                  right: 1px;
                  bottom: 1px;
                  @include flexcolumn-sb;

                  .spin {
                    color: lighten($color-darkgrey, 20%);
                    background-color: transparent;
                    border: none;
                    border-left:1px solid lighten($color-darkgrey, 60%);
                    width: 40px;
                    height: 50%;
                    cursor: pointer;

                    &:last-child {
                      border-top: 1px solid lighten($color-darkgrey, 60%);
                    }

                    &:focus {
                      outline: 0;
                    }
                  }
                }
              }                   
            }
        }

        .add-button-container {
          @include flexrow-sb;
          flex-wrap: wrap;

          @include media-query(small) {
            @include flexrow-cc;
            margin-bottom: 30px;
          }

            .btn {
              @include secondary-button;
              margin-top: 15px;
              font-size: 1.2em;

              .icon {
                margin-right: 10px;
              }
            }

            .btn--no-border {
              border-style: none;
              padding: 10px 15px 10px 0px;

              &:hover {
                background-color: $color-white;
                color: $color-darkgrey;
              }
            }
        }
      }
  }
</style>
