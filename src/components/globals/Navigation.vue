<template>
  <div class="nav-container">

    <!-- The dark grey bar at the top of the page -->
    <nav class="top-nav">
      <div class="wrapper-small">
        <div class="currency-container">
          <label id="currency-label" for="currency">Currency :</label>
          <select id="currency" name="currency">
            <option selected="selected" value="GBP">GDP</option>
            <option value="EUR">EUR</option>
            <option value="DKK">DKK</option>
          </select>
        </div>
        <div class="route-container">
          <router-link class="route" to="/authenticate">Register</router-link>
          <router-link class="route" to="/authenticate">Sign In</router-link>
          <div class="cart-container">
            <button class="cart-container__button"><i class="cart fas fa-shopping-cart"></i>empty<i class="arrow fas fa-angle-down"></i></button>
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

    <!-- Navigation to be displayed on mobile -->
    <!-- Note: Quick make, very messy, make new solution if time -->
    <nav class="mobile-btm-nav">
        <router-link class="logo" to="/">AVENUE FASHION</router-link>
        <button v-on:click="showMobileMenu = !showMobileMenu" class="burger" v-bind:class="[ showMobileMenu === true ? 'open' : '' ]"></button>
      <div class="burger-menu-content" v-if="showMobileMenu">
        <button class="backButton" v-if="!mainRouteContent" v-on:click="mainRouteContent = true; nestedRoutes = false"><i class="fas fa-arrow-left"></i></button>
        <ul class="burger-menu-content__routes-container" v-if="mainRouteContent">
          <li class="routes-container__item arrow" v-on:click="mainRouteContent = false; nestedRoutes = true">MENS<i class="icon fas fa-angle-right"></i></li>
          <li class="routes-container__item arrow" v-on:click="mainRouteContent = false; nestedRoutes = true">WOMENS<i class="icon fas fa-angle-right"></i></li>
          <li class="routes-container__item" v-on:click="showMobileMenu = false"><router-link class="route" to="/brand">THE BRAND</router-link></li>
          <li class="routes-container__item arrow" v-on:click="mainRouteContent = false; nestedRoutes = true">LOCAL STORES<i class="icon fas fa-angle-right"></i></li>
          <li class="routes-container__item arrow" v-on:click="mainRouteContent = false; nestedRoutes = true">LOOK BOOK<i class="icon fas fa-angle-right"></i></li>
        </ul>
        <!-- Note: If time make it so that the nested routes shown belongs to the parent clicked -->
        <ul class="nested-routes-container" v-if="nestedRoutes">
            <li class="nested-routes-container__item">Rand 1</li>
            <li class="nested-routes-container__item">Rand 2</li>
            <li class="nested-routes-container__item">Rand 3</li>
            <li class="nested-routes-container__item">Rand 4</li>
            <li class="nested-routes-container__item">Rand 5</li>
            <li class="nested-routes-container__item">Rand 6</li>
        </ul>
      </div>
    </nav>

  </div>
</template>

<script>

export default {
  name: 'Navigation',
  data: function() {
    return {
      // This should be altered to just use numbers, like the tabs.
      showDropDownMens: false,
      showDropDownWomens: false,
      showDropDownStores: false,
      showDropDownLookbook: false,
      showDropDownCurrency: false,

      // Mobile menu not displayed at first
      showMobileMenu: false,
      // Mobile menu main content displayed at first
      mainRouteContent: true,
      // Mobile menu nested routes
      nestedRoutes: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  @import "../../styles/utilities/mixins.scss";
  @import "../../styles/utilities/vars.scss";

  .mobile-btm-nav {
    position: relative;
    height: 60px;
    padding: 0px 20px 0px 20px;
    display: none;

    @include media-query(small) {
      @include flexrow-sbcv;
    }

      .logo {
        text-decoration: none;
        font-family: $font-sec;
        font-size: 1em;
        white-space: nowrap;
        color: $color-darkgrey;
      }

      .burger {
        border: 0;
        background: none;
        outline: 0;
        padding: 0;
        cursor: pointer;
        border-bottom: 4px solid $color-darkgrey;
        width: 28px;
        transition: border-bottom 1s ease-in-out;
        -webkit-transition: border-bottom 1s ease-in-out;
        z-index: 9999;

        &::-moz-focus-inner {
          border: 0;
          padding: 0;
        }	 

        &:before {
          content: "";
          display: block;
          border-bottom: 4px solid $color-darkgrey;
          width: 100%;
          margin-bottom: 5px;
          transition: transform 0.5s ease-in-out;    
          -webkit-transition: -webkit-transform 0.5s ease-in-out;        
        }

        &:after {
          content: "";
          display: block;
          border-bottom: 4px solid $color-darkgrey;
          width: 100%;
          margin-bottom: 5px;
          transition: transform 0.5s ease-in-out;
          -webkit-transition: -webkit-transform 0.5s ease-in-out;
        }

	      &.open {
	      	border-bottom: 4px solid $color-cyan;
          position: fixed;
          right: 20px;

		      &:before {
			      transform: rotate(-405deg) translateY(1px) translateX(-3px);
		      	-webkit-transform: rotate(-405deg) translateY(1px) translateX(-3px);      
		      	transition: transform 0.5s ease-in-out;
		      	-webkit-transition: -webkit-transform 0.5s ease-in-out;
		      }

		      &:after {
			      transform: rotate(405deg) translateY(-4px) translateX(-5px); 
		      	-webkit-transform: rotate(405deg) translateY(-4px) translateX(-5px);       
		      	transition: transform 0.5s ease-in-out;
		      	-webkit-transition: -webkit-transform 0.5s ease-in-out;
	      	}
	      }
      }

      .burger-menu-content {
        position: relative;
        position: fixed;
        overflow: hidden;
        @include flexrow-cc;
        background-color: $color-lightgrey;
        height: 100%;
        width: 100%;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        z-index: 1;

        .backButton {
          position: absolute;
          background-color: inherit;
          color: $color-darkgrey;
          font-size: 1.6em;
          border: none;
          top: 50px;
          left: 15px;

          &:hover {
            color: $color-cyan;
          }
        }

        .burger-menu-content__routes-container {
          width: 100%;
          height: 50%;
          margin-left: 20px;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          align-items: flex-start;
          list-style-type: none;

          .routes-container__item {
            text-decoration: none;
            color: $color-darkgrey;
            cursor: pointer;
            font-family: $font-main;

            &:hover {
              color: $color-cyan;
            }

            &:hover .icon {
              color: $color-cyan;
            }

            .route {
              font-family: $font-main;
              text-decoration: none;
              all: unset;
            }

            .icon {
              margin-left: 5px;
              color: $color-darkgrey;
            }
          }
        }

        .nested-routes-container {
          width: 100%;
          height: 50%;
          margin-left: 20px;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          align-items: flex-start;
          list-style-type: none;

          .nested-routes-container__item {
            text-decoration: none;
            color: $color-darkgrey;
            cursor: pointer;
            font-family: $font-main;

            &:hover {
              color: $color-cyan;
            }

            &:hover .icon {
              color: $color-cyan;
            }

            .route {
              font-family: $font-main;
              text-decoration: none;
              all: unset;
            }
          }
        }
      }
  }

  .nav-container {
    @include flexcolumn;
    min-width: $width-medium;

    @include media-query(small) {
      min-width: $width-small;
    }

      .top-nav {
        height: 40px;
        background-color: darken($color-darkgrey, 10%);

    .wrapper-small {
      position: relative;
      margin: auto;
      width: $width-medium;
      height: 100%;
      @include flexrow-sbcv;

      @include media-query(small) {
        width: 100%;
      }

        .currency-container {
          position: relative;
          color: lighten($color-darkgrey, 45%);
          font-weight: bold;
          font-family: $font-main;
          white-space: nowrap;

          @include media-query(small) {
            padding-left: 20px;
          }


        select {
          color: lighten($color-darkgrey, 45%);
          font-family: $font-main;
          font-weight: bold;
          background-color: transparent;
          border-color: transparent;

          &:focus {
            outline: none;
          }
          option {
            background-color: darken($color-darkgrey, 10%);
          }
        }
      }

      .route-container {
        height: 100%;
        @include flexrow-cv;

        .route {
          white-space: nowrap;
          color: lighten($color-darkgrey, 45%);
          margin-right: 15px;
          text-decoration: none;
          font-family: $font-sec;

          &:hover {
            color: $color-cyan;
          }

          @include media-query(small) {
            display: none;
          }
        }

        .cart-container {
          height: 100%;
          margin-left: 40px;
          
          .cart-container__button {
            color: $color-white;
            height: 100%;
            background-color: $color-cyan;
            border-color: transparent;
            cursor: pointer;
            padding: 0px 20px 0px 20px;
            display: flex;
            
            .cart {
              margin-right: 10px;
            }

            .arrow {
              align-self: center;
              margin-left: 5px;
            }
          }
        }
      }

  }

    }
  

  .bottom-nav {
    position: relative;
    height: 120px;
    background-color: $color-lightgrey;

    @include media-query(small) {
      display: none;
    }

    .wrapper-large {
      position: relative;
      margin: auto;
      height: 100%;
      padding: 0px 20px 0px 20px;
      @include flexrow-ce;
      max-width: $width-big;
      height: 100%;


      .logo {
        margin-right: auto;
        text-decoration: none;
        font-family: $font-sec;
        font-size: 1.5em;
        white-space: nowrap;
        color: $color-darkgrey !important;
      }

      .search-input {
        margin-left: 60px;
        padding: 5px;
      }

      .menu-item {
        padding: 30px 0px 30px 0px;
        margin-left: 30px;
        text-decoration: none;
        font-family: $font-sec;
        color: #222222;
        white-space: nowrap;
        font-weight: bold;

        &:hover {
          color: $color-cyan;
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
          @include flexrow-sa;
          flex-wrap: wrap;
          min-width: 380px;
          margin: 30px 0px 0px 30px;
          position: absolute;
          background-color: $color-lightgrey;
          box-shadow: 0px 6px 15px 2px rgba(0,0,0,0.21);
          z-index: 1;

          .dropdown-content-row {
            padding: 20px;
            @include flexcolumn;

            .dropdown-content-row__heading {
              margin-bottom: 10px;
              color: $color-darkgrey;
            }

            .dropdown-content-row__item {
              margin-top: 8px;
              text-decoration: none;
              color: lighten($color-darkgrey, 20%);

              &:hover {
                color: $color-cyan;
              }
            }
          }         
        }
      }

      .router-link-active {
        color: $color-cyan;
      }
    }
  }
}

</style>
