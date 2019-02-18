<template>
  <div class="nav-container">

    <!-- The dark grey bar at the top of the page -->
    <nav class="top-nav">
      <div class="wrapper-small">
        <div class="dropdown" v-on:click="showDropDownCurrency = !showDropDownCurrency">
          <button>Currency: <span></span></button>
          <div class="dropdown__content" v-if="showDropDownCurrency">
            <div class="dropdown-content-row">
             <h5 class="dropdown-content-row__heading">CASUALS</h5>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <!-- The white bar with all the different routes, second from the top of the page -->
    <nav class="bottom-nav">
      <div class="wrapper-large">
        <router-link class="logo" to="/">AVENUE FASHION</router-link>

        <div class="dropdown" @mouseover="showDropDownMens = true" @mouseleave="showDropDownMens = false">
          <router-link class="menu-item arrow" to="/mens">MENS</router-link>
          <div class="dropdown__content" v-if="showDropDownMens">
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">CASUALS</h5>
              <router-link class="dropdown-content-row__item" to="/">Jackets</router-link>
              <router-link class="dropdown-content-row__item" to="/">Hoodies &amp; Sweatshirts</router-link>
              <router-link class="dropdown-content-row__item" to="/">Polo Shirts</router-link>
              <router-link class="dropdown-content-row__item" to="/">Sportswear</router-link>
              <router-link class="dropdown-content-row__item" to="/">Trousers &amp; Chinos</router-link>
              <router-link class="dropdown-content-row__item" to="/">T-Shirts</router-link>
            </div>
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">FORMAL</h5>
              <router-link class="dropdown-content-row__item" to="/">Jackets</router-link>
              <router-link class="dropdown-content-row__item" to="/">Shirts</router-link>
              <router-link class="dropdown-content-row__item" to="/">Suits</router-link>
              <router-link class="dropdown-content-row__item" to="/">Trousers</router-link>
            </div>


              <div class="ad-container"></div>
          </div>
        </div>

        <div class="dropdown" @mouseover="showDropDownWomens = true" @mouseleave="showDropDownWomens = false">
          <router-link class="menu-item arrow" to="#">WOMENS</router-link>
                    <div class="dropdown__content" v-if="showDropDownWomens">
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">CASUALS</h5>
              <router-link class="dropdown-content-row__item" to="/">Jackets</router-link>
              <router-link class="dropdown-content-row__item" to="/">Hoodies &amp; Sweatshirts</router-link>
              <router-link class="dropdown-content-row__item" to="/">Polo Shirts</router-link>
              <router-link class="dropdown-content-row__item" to="/">Sportswear</router-link>
              <router-link class="dropdown-content-row__item" to="/">Trousers &amp; Chinos</router-link>
              <router-link class="dropdown-content-row__item" to="/">T-Shirts</router-link>
            </div>
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">FORMAL</h5>
              <router-link class="dropdown-content-row__item" to="/">Dresses</router-link>
              <router-link class="dropdown-content-row__item" to="/">Shirts</router-link>
              <router-link class="dropdown-content-row__item" to="/">Suits</router-link>
              <router-link class="dropdown-content-row__item" to="/">Trousers</router-link>
            </div>


              <div class="ad-container"></div>
          </div> 
        </div>
        
        <router-link class="menu-item" to="/brand">THE BRAND</router-link>

        <div class="dropdown" @mouseover="showDropDownStores = true" @mouseleave="showDropDownStores = false">
          <router-link class="menu-item arrow" to="#">LOCAL STORES</router-link>
          <div class="dropdown__content" v-if="showDropDownStores">
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">Zealand</h5>
              <router-link class="dropdown-content-row__item" to="#">Copenhagen</router-link>
              <router-link class="dropdown-content-row__item" to="#">Roskilde</router-link>
            </div>
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">Funen</h5>
              <router-link class="dropdown-content-row__item" to="#">Odense</router-link>
            </div>
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">Jutland</h5>
              <router-link class="dropdown-content-row__item" to="#">Aarhus</router-link>
              <router-link class="dropdown-content-row__item" to="#">Aalborg</router-link>
              <router-link class="dropdown-content-row__item" to="#">Frederecia</router-link>
            </div>
          </div>
        </div>

        <div class="dropdown" @mouseover="showDropDownLookbook = true" @mouseleave="showDropDownLookbook = false">
          <router-link class="menu-item arrow" to="#">LOOK BOOK</router-link>
          <div class="dropdown__content" v-if="showDropDownLookbook">
            <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">Zealand</h5>
              <router-link class="dropdown-content-row__item" to="#">Copenhagen</router-link>
              <router-link class="dropdown-content-row__item" to="#">Roskilde</router-link>
            </div>
                        <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">Zealand</h5>
              <router-link class="dropdown-content-row__item" to="#">Copenhagen</router-link>
              <router-link class="dropdown-content-row__item" to="#">Roskilde</router-link>
            </div>
                        <div class="dropdown-content-row">
              <h5 class="dropdown-content-row__heading">Zealand</h5>
              <router-link class="dropdown-content-row__item" to="#">Copenhagen</router-link>
              <router-link class="dropdown-content-row__item" to="#">Roskilde</router-link>
            </div>
          </div>
        </div>

        <input type="search" class="search-input" aria-label="Search site content" placeholder="Search...">
      </div>
    </nav>
  </div>
</template>

<script>

export default {
  name: 'Navigation',
  data: function() {
    return {
      showDropDownMens: false,
      showDropDownWomens: false,
      showDropDownStores: false,
      showDropDownLookbook: false,
      showDropDownCurrency: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.nav-container {
  display: flex;
  flex-direction: column;
  flex: 1;

  .top-nav {
    height: 40px;
    background-color: #333333;

    .wrapper-small {
      position: relative;
      margin: auto;
      max-width: 1024px;
      height: 100%;
      display: flex;
      justify-content: flex-end;
      align-items: center;
    }
  }

  .bottom-nav {
    height: 120px;
    background-color: #f8f8f8;

    .wrapper-large {
      position: relative;
      margin: auto;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: flex-end;
      max-width: 1440px;
      height: 100%;

      .logo {
        margin-right: auto;
        text-decoration: none;
        font-family: 'Roboto', sans-serif;
        font-size: 1.5em;
        white-space: nowrap;
        color: #222222 !important;
      }

      .search-input {
        margin-left: 60px;
        padding: 5px;
      }

      .menu-item {
        padding: 30px 0px 30px 0px;
        margin-left: 30px;
        text-decoration: none;
        font-family: 'Roboto', sans-serif;
        color: #222222;
        white-space: nowrap;
        font-weight: bold;

        &:hover {
          color: #00c8c8;
        }
      }
      
      .arrow {


        &::after {
          display: flex;
          margin-top: 3px;
          margin-left: 30px;
          position: absolute;
          font-family: "Font Awesome 5 Free";
          content: "\f107";
          width: 100%;
        }
      }

      .dropdown {
        position: relative;


        .dropdown__content {
          display: flex;
          justify-content: space-around;
          flex-wrap: wrap;
          min-width: 380px;
          margin: 30px 0px 0px 30px;
          position: absolute;
          background-color: #f8f8f8;
          box-shadow: 0px 6px 15px 2px rgba(0,0,0,0.21);
          z-index: 1;

          .dropdown-content-row {
            padding: 20px;
            display: flex;
            flex-direction: column;

            .dropdown-content-row__heading {
              margin-bottom: 10px;
              color: #575153;
            }

            .dropdown-content-row__item {
              margin-top: 8px;
              text-decoration: none;
              color: #727272;

              &:hover {
                color: #00c8c8;
              }
            }
          }

          
        }
      }


      .router-link-active {
        color: #00c8c8;
      }
    }
  }
}

</style>
