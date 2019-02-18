<template>
    <footer class="footer">
      <div class="wrapper">
        <ul class="list-container">
          <h5 class="list-container__heading">INFORMATION</h5>
          <li class="list-container__item">The brand</li>
          <li class="list-container__item">Local stores</li>
          <li class="list-container__item">Customer service</li>
          <li class="list-container__item">Privacy &amp; cookies</li>
          <li class="list-container__item">Sitemap</li>
        </ul>
        <ul class="list-container">
          <h5 class="list-container__heading">WHY BUY FROM US</h5>
          <li class="list-container__item">Shipping &amp; returns</li>
          <li class="list-container__item">Secure shopping</li>
          <li class="list-container__item">Testimonials</li>
          <li class="list-container__item">Award winning</li>
          <li class="list-container__item">Ethical trading</li>
        </ul>
        <ul class="list-container">
          <h5 class="list-container__heading">YOUR ACCOUNT</h5>
          <li class="list-container__item">Sign in</li>
          <li class="list-container__item">Register</li>
          <li class="list-container__item">View cart</li>
          <li class="list-container__item">View your lookbook</li>
          <li class="list-container__item">Track an order</li>
          <li class="list-container__item">Update information</li>
        </ul>
        <ul class="list-container">
          <h5 class="list-container__heading">LOOKBOOK</h5>
          <li class="list-container__item">Latest posts</li>
          <li class="list-container__item">Men's lookbook</li>
          <li class="list-container__item">Women's lookbook</li>
          <li class="list-container__item">Lookbooks RSS feed</li>
          <li class="list-container__item">View your lookbook</li>
          <li class="list-container__item">Delete your lookbook</li>
        </ul>
         <ul class="list-container">
          <h5 class="list-container__heading">CONTACT DETAILS</h5>
          <li class="list-container__item">Head Office: Avenue Fashion<br>180-182 Regent Street, London</li>
          <li class="list-container__item">Telephone: 0123-456-789</li>
          <li class="list-container__item">Email: support@yourwebsite.com</li>
        </ul>

        <div class="block-container">
          <div class="award-container">
              <h1 class="award-container__heading">AWARD WINNER</h1>
              <h1 class="award-container__heading">FASHION AWARDS 2016</h1>
          </div>
          <div class="social-media-container">
              <ul class="social-media-container__list-container">
                <li class="social-media-container__list-container__item"><i class="fab fa-facebook-f"></i></li>
                <li class="social-media-container__list-container__item"><i class="fab fa-twitter"></i></li>
                <li class="social-media-container__list-container__item"><i class="fab fa-instagram"></i></li>
                <li class="social-media-container__list-container__item"><i class="fab fa-pinterest"></i></li>
              </ul>
          </div>
        </div>
      </div>     
    </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.footer {
   background-color: #f8f8f8;

   .wrapper {
     margin: auto;
     max-width: 1024px;
     padding: 30px;
     display: flex;
     justify-content: space-between;
     flex-wrap: wrap;

     @media only screen and (min-width : 320px) and (max-width : 480px) {
          flex-direction: column;
          align-items: center;
      }

     .list-container {
      padding: 0px 0px 20px 0px;
      max-width: 250px;
      min-width: 150px;
      list-style-type: none;

      @media only screen and (min-width : 320px) and (max-width : 480px) {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 250px;
      }

      .list-container__heading {
        margin-bottom: 15px;
        color: #575153;
      }

      .list-container__item {
        margin-bottom: 10px;
        color: #727272;
      }
     }

     .block-container {
       position: relative;
       flex: 0 0 100%;
       display: flex;
       flex-wrap: wrap;
       justify-content: space-between;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
            justify-content: center;
        }

        .award-container {
          display: flex;
          flex: 0 0 45%;
          min-width: 350px;
          height: 100px;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          background-color: #333333;
          padding: 40px 20px 40px 20px;
          line-height: 1.6;
          color: #ffffff;
          white-space: nowrap;

          @media only screen and (min-width : 320px) and (max-width : 480px) {
            min-width: 250px;
            font-size: 0.6em;
            margin-top: 20px;
          }
       }

        .social-media-container {
          background-color: #00c8c8;
          flex: 0 0 45%;
          min-width: 350px;
          height: 100px;
          padding: 40px 20px 40px 20px;

          @media only screen and (min-width : 320px) and (max-width : 480px) {
            margin-top: 25px;
            min-width: 250px;
          }

          .social-media-container__list-container {
            list-style-type:none;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: space-evenly;
            align-items: center;

            .social-media-container__list-container__item {
              font-size: 2em;
              color: #ffffff;
            }
          }
        }
     }
   }
}



</style>
