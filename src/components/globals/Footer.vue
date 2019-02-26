<template>
    <footer class="footer">
      <div class="wrapper">
        <ul class="list-container">
          <h5 class="list-container__heading">INFORMATION</h5>
          <li class="list-container__item"><a href="#">The brand</a></li>
          <li class="list-container__item"><a href="#">Local stores</a></li>
          <li class="list-container__item"><a href="#">Customer service</a></li>
          <li class="list-container__item"><a href="#">Privacy &amp; cookies</a></li>
          <li class="list-container__item"><a href="#">Sitemap</a></li>
        </ul>
        <ul class="list-container">
          <h5 class="list-container__heading">WHY BUY FROM US</h5>
          <li class="list-container__item"><a href="#">Shipping &amp; returns</a></li>
          <li class="list-container__item"><a href="#">Secure shopping</a></li>
          <li class="list-container__item"><a href="#">Testimonials</a></li>
          <li class="list-container__item"><a href="#">Award winning</a></li>
          <li class="list-container__item"><a href="#">Ethical trading</a></li>
        </ul>
        <ul class="list-container">
          <h5 class="list-container__heading">YOUR ACCOUNT</h5>
          <li class="list-container__item"><a href="#">Sign in</a></li>
          <li class="list-container__item"><a href="#">Register</a></li>
          <li class="list-container__item"><a href="#">View cart</a></li>
          <li class="list-container__item"><a href="#">View your lookbook</a></li>
          <li class="list-container__item"><a href="#">Track an order</a></li>
          <li class="list-container__item"><a href="#">Update information</a></li>
        </ul>
        <ul class="list-container">
          <h5 class="list-container__heading">LOOKBOOK</h5>
          <li class="list-container__item"><a href="#">Latest posts</a></li>
          <li class="list-container__item"><a href="#">Men's lookbook</a></li>
          <li class="list-container__item"><a href="#">Women's lookbook</a></li>
          <li class="list-container__item"><a href="#">Lookbooks RSS feed</a></li>
          <li class="list-container__item"><a href="#">View your lookbook</a></li>
          <li class="list-container__item"><a href="#">Delete your lookbook</a></li>
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
                <li class="social-media-container__list-container__item"><a href="#"><i class="fab fa-facebook-f"></i></a></li>
                <li class="social-media-container__list-container__item"><a href="#"><i class="fab fa-twitter"></i></a></li>
                <li class="social-media-container__list-container__item"><a href="#"><i class="fab fa-instagram"></i></a></li>
                <li class="social-media-container__list-container__item"><a href="#"><i class="fab fa-pinterest"></i></a></li>
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
          padding: 30px 0px 30px 0px;
      }

     .list-container {
      margin-bottom: 20px;
      list-style-type: none;

      @media only screen and (min-width : 320px) and (max-width : 480px) {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      .list-container__heading {
        margin-bottom: 15px;
        color: #575153;
      }

      .list-container__item {
        margin-bottom: 10px;
        color: #727272;

        a {
          text-decoration: none;
          color: #727272;

          &:visited {
            color: #727272;
          }
        }
      }
     }

     .block-container {
       position: relative;
       flex: 1;
       display: flex;
       flex-wrap: wrap;
       justify-content: space-between;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
            justify-content: center;
        }

        .award-container {
          display: flex;
          flex: 0 0 45%;
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

                 a {
                  text-decoration: none;
                  color: #ffffff;

                  &:visited {
                    color: #ffffff;
                  }
                }
            }
          }
        }
     }
   }

}



</style>
