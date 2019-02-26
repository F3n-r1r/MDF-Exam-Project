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

    <!-- Navigation to be displayed on mobile -->
    <nav class="mobile-btm-nav">
        <router-link class="logo" to="/">AVENUE FASHION</router-link>
        <button v-on:click="showMobileMenu = !showMobileMenu" class="burger" v-bind:class="[ showMobileMenu === true ? 'open' : '' ]"></button>
      <div class="burger-menu-content" v-if="showMobileMenu">
        <p>dsfdsf</p>
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
      showDropDownCurrency: false,

      showMobileMenu: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.mobile-btm-nav {
    position: relative;
      height: 60px;
      padding: 0px 20px 0px 20px;
      justify-content: space-between;
      align-items: center;
      display: none;

      @media only screen and (min-width : 320px) and (max-width : 480px) {
        display: flex;
      }

      .logo {
        text-decoration: none;
        font-family: 'Roboto', sans-serif;
        font-size: 1em;
        white-space: nowrap;
        color: #222222 !important;
      }
}


.burger-menu-content {
     position: fixed;
     overflow: hidden;
    background-color: #f8f8f8;
    height: 100%;
    width: 100%;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
}

.burger {
  border: 0;
  background: none;
  outline: 0;
  padding: 0;
  cursor: pointer;
  border-bottom: 4px solid #222222;
  width: 28px;
  transition: border-bottom 1s ease-in-out;
  -webkit-transition: border-bottom 1s ease-in-out;
  z-index: 9999;


  	// Fix for extra space in Firefox
	&::-moz-focus-inner {
		border: 0;
		padding: 0;
	}	 

	&:before {
		content: "";
		display: block;
		border-bottom: 4px solid #222222;
		width: 100%;
		margin-bottom: 5px;
		transition: transform 0.5s ease-in-out;    
		-webkit-transition: -webkit-transform 0.5s ease-in-out;        
	}

	&:after {
		content: "";
		display: block;
		border-bottom: 4px solid #222222;
		width: 100%;
		margin-bottom: 5px;
		transition: transform 0.5s ease-in-out;
		-webkit-transition: -webkit-transform 0.5s ease-in-out;
	}

	&.open {
		border-bottom: 4px solid #00c8c8;
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



.nav-container {
  display: flex;
  flex-direction: column;
  min-width: 1024px;

  @media only screen and (min-width : 320px) and (max-width : 480px) {
      min-width: 320px;
  }

  .top-nav {
    height: 40px;
    background-color: #333333;

    .wrapper-small {
      position: relative;
      margin: auto;
      width: 1024px;
      height: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;

      @media only screen and (min-width : 320px) and (max-width : 480px) {
        width: 100%;
      }

      .currency-container {
        position: relative;
        color: #777777;
        font-weight: bold;
        font-family: 'Montserrat', sans-serif;
        white-space: nowrap;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
          padding-left: 20px;
        }


        select {
          color: #777777;
          font-family: 'Montserrat', sans-serif;
          font-weight: bold;
          background-color: transparent;
          border-color: transparent;

          &:focus {
            outline: none;
          }
          option {
            background-color: #333333;
          }
        }
      }

      .route-container {
        height: 100%;
        display: flex;
        align-items: center;

        .route {
          white-space: nowrap;
          color: #999999;
          margin-right: 15px;
          text-decoration: none;
          font-family: 'Roboto', sans-serif;

          &:hover {
            color: #00c8c8;
          }


        @media only screen and (min-width : 320px) and (max-width : 480px) {
          display: none;
      }
        }

        .cart-container {
          height: 100%;
          margin-left: 40px;
          
          .cart-container__button {
            color: #ffffff;
            height: 100%;
            background-color: #00c8c8;
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
    background-color: #f8f8f8;

    @media only screen and (min-width : 320px) and (max-width : 480px) {
display: none;
    }

    .wrapper-large {
      position: relative;
      margin: auto;
      height: 100%;
      padding: 0px 20px 0px 20px;
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
