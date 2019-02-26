<template>
  <div class="auth-container">
    <Header v-bind:HeadlineOne="HeadlineOne" v-bind:HeadlineTwo="HeadlineTwo"/>

    <div class="error-container" v-if="errors.length">
      <p>Please correct the following errors:</p>
      <ul class="error-list">
        <li class="error-list--item" v-for="error in errors" v-bind:key="error">- {{error}}</li>
      </ul>
    </div>

    <section class="section-main">
      <div class="form-container">
        
        <form class="form" action="" @submit="checkLogin" novalidate="true">
          <h3 class="headline">SIGN IN</h3>
          <input class="form__input" type="email" name="email" placeholder="Your Email.." v-model="signinemail" v-bind:class="{error: signinemailerr}">
          <input class="form__input" type="password" name="password" placeholder="Your Password" v-model="signinpassword" v-bind:class="{error: signinpasserr}">
          <div class="row">
            <input class="btn small" type="submit" value="SIGN IN">
            <a class="link" href="#">Forgot your password <i class="icon fas fa-long-arrow-alt-right"></i></a>
          </div>
        </form>
      </div>

      <div class="vl"></div>

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
            <input class="btn big" type="submit" value="CREATE ACCOUNT">
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

      // In real application: Find mail in the database, if found then compare password and create token.
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

      // In real application: Call function to store email and a hashed version of the password in the database
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

.error-container {
  display: flex;
  padding: top;
  margin:  20px auto 0px auto;
  padding: 10px;
  flex-direction: column;
  max-width: 1024px;
  background-color: #fcf6f7;
  border: 1px solid #bb5465;

  .error-list {
    margin-top: 10px;
    list-style-type: none;

    .error-list__item {
      list-style-type: none;
    }
  }
}

.error {
  background-color: #fcf6f7;
  border: 1px solid #bb5465;
}

.section-main {
  margin: auto;
  width: 1024px;
  display: flex;
  justify-content: center;
    
  @media only screen and (min-width : 320px) and (max-width : 480px) {
      flex-direction: column;
      align-items: center;
      width: 320px;
      padding-bottom: 50px;
  }




  .form-container {
    padding: 50px 20px 50px 20px;
    width: 100%;

    @media only screen and (min-width : 320px) and (max-width : 480px) {
      flex-direction: column;
      align-items: center;
      width: 320px;
      padding: 50px 0px 0px 0px;
  }

    .form {
      display: flex;
      flex-direction: column;

      @media only screen and (min-width : 320px) and (max-width : 480px) {
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
        border: 1px solid #8e8c8c;
        content: "\00a0";
        display: inline-block;
        height: 16px;
        margin: 0px 15px 0px 0px;
        vertical-align: top;
        width: 16px;
      }
      input[type="checkbox"]:checked + label:before {
        background: #fff;
        content: "\2713";
        text-align: center;
      }
      input[type="checkbox"]:checked + label:after {
        font-weight: bold;
      }

      .label {
        color: #8e8c8c;
        font-family: 'Montserrat', sans-serif;
        font-size: 0.7em;
        white-space: nowrap;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
          white-space:pre-wrap;
        }
      }



      .row {
        margin-top: 25px;
        display: flex;
        justify-content: space-between;
        align-items: center;

        .btn {
          color: #454647;
          white-space: nowrap;
          font-weight: bold;
          border: 1px solid #454647;
          background-color: #f8f8f8;
          margin-right: 10px;
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

          .big {
            width: 200px;
          }
          .small {
            width: 100px;
          }
        }

        .link {
          text-decoration: none;
          color: #00c8c8;
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

  .vl {
    position: relative;
    height: 100%;
    border-right: 6px solid red;
  }


}

</style>
