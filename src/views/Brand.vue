<template>
  <div class="product">
    <Header v-bind:HeadlineOne="HeadlineOne" v-bind:HeadlineTwo="HeadlineTwo"/>
    <section class="brand-section">
sdfgfd
    </section>
  </div>
</template>


<script>
import Header from '@/components/globals/Header.vue'
export default {
  components: {
    Header
  },
  data: function() {
    return {
      HeadlineOne: 'THE BRAND',
      HeadlineTwo: 'COMPANY SLOGAN GOES HERE',
    }
  }
}
</script>


<style scoped lang="scss">

.brand-section {
  margin: auto;
  max-width: 1024px;
  padding: 30px;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

</style>
