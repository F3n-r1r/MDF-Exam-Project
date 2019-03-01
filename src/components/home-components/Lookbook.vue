<template>
    <section class="lookbook-section">

      <div class="lookbook-section__container">
        <img class="lookbook-quickView__element__img" src="@/assets/lookbookMan.png" alt="A well dressed man">
        <div class="lookbook-quickView__element__info">
          <h3 class="look-quickView-heading--bold">MEN'S</h3>
          <h3 class="look-quickView-heading">LOOKBOOK</h3>
          <p class="look-quickView-text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia repudiandae nam aliquid magnam provident.</p>
          <button class="look-quickView-btn">VIEW NOW</button>
        </div>
      </div>

      <div class="lookbook-section__container">
        <img class="lookbook-quickView__element__img" src="@/assets/lookbookMan.png" alt="A well dressed man">
        <div class="lookbook-quickView__element__info">
          <h3 class="look-quickView-heading--bold">WOMEN'S</h3>
          <h3 class="look-quickView-heading">LOOKBOOK</h3>
          <p class="look-quickView-text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia repudiandae nam aliquid magnam provident.</p>
          <button class="look-quickView-btn">VIEW NOW</button>
        </div>
      </div>

      <div class="lookbook-section__container">
        <img class="lookbook-quickView__element__img" src="@/assets/lookbookMan.png" alt="A well dressed man">
        <div class="lookbook-quickView__element__info">
          <h3 class="look-quickView-heading--bold">YOUR</h3>
          <h3 class="look-quickView-heading">LOOKBOOK</h3>
          <p class="look-quickView-text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia repudiandae nam aliquid magnam provident.</p>
          <button class="look-quickView-btn">VIEW NOW</button>
        </div>
      </div>

    </section>
</template>


<script>
export default {
    name: 'Lookbook',
}
</script>


<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";

  .lookbook-section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
    grid-gap: 10px;
    margin: 0px auto 75px auto;

    @include media-query(small) {
      min-width: $width-small;
      @include flexcolumn-cv;
    }

      .lookbook-section__container {
        background-color: $color-lightgrey;
        padding: 50px 20px 0px 20px;
        display: flex;
        justify-content: space-around;

        @include media-query(small) {
          max-width: $width-small;
          margin-top: 20px;
          padding: 20px 0px 20px 0px;
        }

          .lookbook-quickView__element__img {
            height: 400px;
            margin-top: 0;

            @include media-query(small) {
              display: none;
            }
          }

          .lookbook-quickView__element__info {
            @include flexcolumn;

            .look-quickView-heading--bold {
              margin-left: auto;
              font-size: 3em;
              color: $color-darkgrey;
              font-family: $font-sec;

              @include media-query(small) {
                margin: auto;
              }
            }

            .look-quickView-heading {
              margin-left: auto;
              font-size: 3em;
              color: $color-darkgrey;
              font-family: $font-main;

              @include media-query(small) {
                margin: auto;
              }
            }

            .look-quickView-text {
              text-align: right;
              margin-top: 30px;

              @include media-query(small) {
                text-align: center;
              }
            }

            .look-quickView-btn {
              @include primary-button;
              margin-left: auto;
              margin-top: 40px;

              @include media-query(small) {
                margin: auto;
                margin-top: 40px;
              }
            }
          }
      }
  }

</style>
