<template>
  <div class="home">

    <section class="banner">
      <div class="wrapper">
        <h1 class="companyLogo"><span>A</span><span>V</span><span>E</span></h1>
        <button class="primary-btn">SHOP MEN'S COLLECTION</button>
      </div>    
    </section>

  <Products />

  <Lookbook />

  </div>
</template>

<script>
// @ is an alias to /src
import Lookbook from '@/components/home-components/Lookbook.vue'
import Products from '@/components/home-components/Products.vue'

export default {
    components: {
      Lookbook,
      Products
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.home {
  background-color: #ffffff;
}

// MOVE BACKGROUND INSIDE WRAPPER INSTEAD!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
  .banner {
    position: relative;
    background-image: url("../assets/bgImgHomeLarge.png");
    height: 920px;
    background-color: #f8f8f8;
    background-position: left;
    background-repeat: no-repeat;
    display: flex;
    justify-content: center;
    align-items: center;

    @media only screen and (min-width : 481px) and (max-width : 1024px) {
        background-image: url("../assets/bgImgHomeMedium.png");
        height: 690px;
    }
    
    @media only screen and (min-width : 320px) and (max-width : 480px) {
        background-image: url("../assets/bgImgHomeSmall.png");
        height: 460px;
    }
  }

.wrapper {
  position: relative;
  width: 1440px;
  height: 80%;
  padding: 50px;
  display: flex;
  justify-content: center;
  align-items: center;

  .companyLogo {
    font-size: 20em;
    color: #575153;
    display: flex;
    justify-content: space-between;
    width: 100%;

    @media only screen and (min-width : 481px) and (max-width : 1024px) {
        font-size: 15em;
    }
    
    @media only screen and (min-width : 320px) and (max-width : 480px) {
        font-size: 5em;
    }
  }

  .primary-btn {
    position: absolute;
    right: 10px;
    align-self: flex-end;
    color: #454647;
    white-space: nowrap;
    font-weight: bold;
    border: 1px solid #454647;
    background-color: #f8f8f8;
    padding: 15px 25px 15px 25px;
    font-family: 'Montserrat', sans-serif;

    &:focus {
      outline: none;
    }

    &:hover {
      cursor: pointer;
      background-color: #00c8c8;
      color: #ffffff;
    }
  }
}


</style>
