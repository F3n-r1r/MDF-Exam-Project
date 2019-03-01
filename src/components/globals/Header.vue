<template>
    <header class="header">
        <div class="overlay">
            <h1 class="headline big">{{HeadlineOne}}</h1>
            <h2 class="headline small">{{HeadlineTwo}}</h2>
        </div>
    </header> 
</template>

<script>
export default {
    name: 'Header',
    props: ['HeadlineOne', 'HeadlineTwo']
}
</script>


<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";

  .header {
    background-image: url('../../assets/bannerBg.jpg');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    height: 450px;

    .overlay {
      background-color: rgba(97, 97, 97, 0.8);
      height: 100%;
      width: 100%;
      @include flexcolumn-cc;

      .headline {
        color: $color-white;
        font-family: $font-main;
        white-space: nowrap;
      }

      .big {
        font-size: 4em;

        @include media-query(small) {
          font-size: 2em;
        }
      }

      .small {
        font-size: 2em;
        margin-top: 20px;

        @include media-query(small) {
          font-size: 1em;
        }
      }
    }
  }

</style>
