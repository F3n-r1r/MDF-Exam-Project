<template>
  <div id="app">
    <Navigation />

    
    <router-view/>


    <Footer />

  </div>
</template>

<script>
// @ is an alias to /src
import Footer from '@/components/globals/Footer.vue'
import Navigation from '@/components/globals/Navigation.vue'     
export default {
  name: 'app',
  components: {
    Footer,
    Navigation
  }
}
</script>



<style lang="scss">

  @import "./styles/utilities/mixins.scss";
  @import "./styles/utilities/vars.scss";

  * {
    padding: 0;
    margin: 0;
  }

  #app {
    min-width: $width-big;

      @include media-query(small) {
        min-width: $width-small;
      }
  }

  h1, h2, h3, h4, h5, h6 {
    font-family: $font-sec;
  }

  p {
    font-family: $font-main;
  }

</style>
