<template>

    <div class="carousel-container">

        <div class="img-container">

            <img class="img-container__img" v-bind:src="require('@/assets/' + currentImage)" alt="">

            <div class="img-container__actions-container">

                <span @click="prevImage" class="actions-container__action">
                    <i class="action__icon fas fa-chevron-left"></i>
                </span>

                <span @click="nextImage" class="actions-container__action">
                    <i class="action__icon fas fa-chevron-right"></i>
                </span>

            </div>

        </div>

    </div>

</template>


<script>

export default {
    name: 'ProductImgSlider',

    data: function() {
        return {
            images: [
                {
                    id: '1',
                    img: 'productPageImg.jpg'
                },
                {
                    id: '2',
                    img: 'product1.jpg'
                },
                {
                    id: '3',
                    img: 'product2.jpg'
                },
                {
                    id: '4',
                    img: 'product3.jpg'
                }
            ],
            activeImage: 0
        }
    },

    computed: {
        currentImage() {
            return this.images[this.activeImage].img;
        }
    },

    methods: {
        nextImage() {
            var active = this.activeImage + 1;
            if(active >= this.images.length) {
                active = 0;
            }
            this.activateImage(active);
        },

        prevImage() {
            var active = this.activeImage - 1;
            if(active < 0) {
                active = this.images.length - 1;
            }
            this.activateImage(active);
        },

        activateImage(imageIndex) {
            this.activeImage = imageIndex;
        }
    }
}
</script>


<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";

  .carousel-container {
    grid-column: span 6;
    position: relative;
    user-select: none;

    @include media-query(small) {
      max-width: $width-small;
    }

      .img-container {
        position: absolute;
        width: 100%;
        height: 100%;
        @include flexrow-ch;
        overflow: hidden;

        @include media-query(small) {
          position: relative;
          height: 400px;
        }

          .img-container__img {
            position: relative;
            height: 100%;

            @include media-query(small) {
              object-fit: fill;
            }
          }

          .img-container__actions-container {
            font-size: 1.5em;
            position: absolute;
            top: 50%;
            width: 100%;
            @include flexrow-sbcv;
            color: $color-darkgrey;

            .actions-container__action {
              cursor: pointer;
              padding: 8px;

              &:hover {
                color: $color-white;
                background-color: $color-cyan;
              }

              .action__icon {
                font-size: 1.3em;
              }
            }
          }
      }
  }

</style>
