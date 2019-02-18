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
* {
  padding: 0;
  margin: 0;
}




h1, h2, h3, h4, h5, h6 {
  font-family: 'Roboto', sans-serif;
}

p {
  font-family: 'Montserrat', sans-serif;

}
</style>
