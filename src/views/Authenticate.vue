<template>
  <div class="auth-container">
    
    <Header v-bind:HeadlineOne="HeadlineOne" v-bind:HeadlineTwo="HeadlineTwo"/>

    <div class="error-container" v-if="errors.length">
      <p>Please correct the following errors:</p>
      <ul class="error-container__error-list">
        <li v-for="error in errors" v-bind:key="error">- {{error}}</li>
      </ul>
    </div>

    <section class="section-main">

      <div class="form-container">
        <form class="form" action="" @submit="checkLogin" novalidate="true">
          <h3 class="headline">SIGN IN</h3>
          <input class="form__input" type="email" name="email" placeholder="Your Email.." v-model="signinemail" v-bind:class="{error: signinemailerr}">
          <input class="form__input" type="password" name="password" placeholder="Your Password" v-model="signinpassword" v-bind:class="{error: signinpasserr}">
          <div class="row">
            <input class="btn" type="submit" value="SIGN IN">
            <a class="link" href="#">Forgot your password <i class="icon fas fa-long-arrow-alt-right"></i></a>
          </div>
        </form>
      </div>

      <div class="form-container">
        <form class="form" action="" @submit="checkRegister" novalidate="true">
          <h3 class="headline">REGISTER</h3>
          <input class="form__input" type="email" name="email" placeholder="Your Email.." v-model="registerEmail" v-bind:class="{error: registeremailerr}">
          <input class="form__input" type="password" name="password" placeholder="Your Password" v-model="registerPassword" v-bind:class="{error: registerpasserr}">
          <input class="form__input" type="password" name="password" placeholder="Confirm Password" v-model="confirmedPassword" v-bind:class="{error: confirmpasserr}">
          <div class="row">
            <input class="form__checkbox" id="checkbox" type="checkbox" name="newsletter">
            <label class="label" for="checkbox">Sign up for exclusive updates, discounts, new arrivals, contests, and more!</label>
          </div>
          <div class="row">
            <input class="btn" type="submit" value="CREATE ACCOUNT">
            <p class="info-text">By clicking 'Create Account', you agree to our <a class="link" href="#">Privacy Policy <i class="icon fas fa-long-arrow-alt-right"></i></a></p>
          </div>
        </form>
      </div>

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
          HeadlineOne: 'WELCOME TO AVE',
          HeadlineTwo: 'SIGN IN OR REGISTER',

          errors: [],

          signinemailerr: false,
          signinpasserr: false,
          signinemail: null,
          signinpassword: null,

          registeremailerr: false,
          registerpasserr: false,
          confirmpasserr: false,
          registerEmail: null,
          registerPassword: null,
          confirmedPassword: null
        }
  },

  methods: {
    checkLogin: function(e) {
      this.errors = [];

      if(!this.signinemail) {
        this.errors.push('Please enter email');
        this.signinemailerr = true;
      } else if(!this.validateEmail(this.signinemail)) {
          this.errors.push('Email is not the right format');
          this.signinemailerr = true;
      }

      if(!this.signinpassword) {
        this.errors.push('Please enter password');
        this.signinpasserr = true;
      }

      if(!this.errors.length) {
        return true;
      }
      e.preventDefault();
    },

    checkRegister: function(e) {
      this.errors = [];

      if(!this.registerEmail) {
        this.errors.push('You need to fill out the email field');
        this.registeremailerr = true;
      } else if(!this.validateEmail(this.registerEmail)) {
          this.errors.push('Email is not the right format');
          this.registeremailerr = true;
      }

      if(!this.registerPassword) {
        this.errors.push('You have to enter a password');
        this.registerpasserr = true;
      } else if(!this.confirmpasserr) {
        this.errors.push('You have to confirm your password');
        this.confirmpasserr = true;
      } else if (!this.validatePassword(this.registerPassword)) {
        this.errors.push('Your password has to be at least 8 characters');
        this.confirmpasserr = true;
        this.registerpasserr = true;
      } else if(this.registerPassword != this.confirmedPassword) {
        this.errors.push('Your passwords does not match');
        this.confirmpasserr = true;
        this.registerpasserr = true;
      }

      if(!this.errors.length) {
        return true;
      }
      e.preventDefault();
    },

    validateEmail: function(email) {
        var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return re.test(email);
    },

    validatePassword: function(password) {
      if(password.length >= 8) {
        return true
      } else {
        return false
      }
    }
  }
}
</script>


<style scoped lang="scss">

  @import "../styles/utilities/mixins.scss";
  @import "../styles/utilities/vars.scss";

  .error-container {
    margin:  20px auto 0px auto;
    padding: 10px;
    max-width: $width-medium;
    background-color: lighten($color-red, 43%);
    border: 1px solid $color-red;

    .error-container__error-list {
      margin-top: 10px;
      list-style-type: none;
    }
  }

  .error {
    background-color: lighten($color-red, 43%);
    border: 1px solid $color-red;
  }

  .section-main {
    margin: auto;
    width: $width-medium;
    @include flexrow-ch;

    @include media-query(small) {
      @include flexcolumn-cv;
      width: $width-small;
      padding-bottom: 50px;
    }
  
      .form-container {
        padding: 50px 20px 50px 20px;
        width: 100%;

        @include media-query(small) {
          width: $width-small;
          padding: 50px 0px 0px 0px;
        }

          .form {
            display: flex;
            flex-direction: column;

            @include media-query(small) {
              padding: 10px;
            }

              .form__input {
                padding: 10px;
                margin-top: 25px;
              }

              input[type="checkbox"] {
                display: none;
              }

              input[type="checkbox"] + label:before {
                border: 1px solid $color-darkgrey;
                content: "\00a0";
                display: inline-block;
                height: 16px;
                margin: 0px 15px 0px 0px;
                vertical-align: top;
                width: 16px;
              }

              input[type="checkbox"]:checked + label:before {
                background: $color-white;
                content: "\2713";
                text-align: center;
              }

              .label {
                color: $color-darkgrey;
                font-family: $font-main;
                font-size: 0.7em;
                white-space: nowrap;

                @include media-query(small) {
                  white-space:pre-wrap;
                }
              }

              .row {
                margin-top: 25px;
                @include flexrow-sbcv;

                .btn {
                  @include primary-button;
                  margin-right: 10px;
                }

                .link {
                  text-decoration: none;
                  color: $color-cyan;
                  white-space: nowrap;

                  .icon {
                    margin-left: 5px;
                  }
                }

                .info-text {
                  font-size: 0.8em;
                  width: 250px;
                }
              }
          }
        }
  }

</style>
