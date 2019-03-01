<template>
  <div class="product">

    <Header v-bind:HeadlineOne="TitleOne" v-bind:HeadlineTwo="TitleTwo"/>

    <section class="brand-section">

      <div class="brand-section__container--1">
        <img class="grid-img" src="../assets/product1.jpg" alt="">
      </div>
      <div class="brand-section__container--2">
        <h4>HAND DESIGNED CLOTHING</h4>
        <h6>ESTABLISHED IN 2013, FASHION SED DICTUM ELIT VEL SAPIEN LUCTUS ERAS</h6>
        <p>
          Praesent feugiat malesuada tristique maecenas rhoncus diam eget quam vestibulim consectetur, id condimentum leo porttitor. Cum sociis natoque penatibus eta magnis disut parturient montes, nascetur ridiculus mus. 
          Donec sem lorem laoreet tempor un risus vitae, rutrum sodales nibh suspendisse congue metus nunc, id viverra elit loreti rhoncus quis consecteur es. Donec pulvinar tempor lorem a pretium justo interdum.
        </p>
      </div>

      <div class="brand-section__container--3">
        <img class="grid-img" src="../assets/product2.jpg" alt="">
      </div>
      <div class="brand-section__container--4">
        <h4>OUR VALUES, VISION AND STRATEGY</h4>
        <h6>THE ABOVE IMAGE WOULD BE A GREAT PLACE FOR AN ADVERTISING VIDEO</h6>
        <p>
          Cras maximus venenatis malesuada. Nulla sagittis elit felis, ac facilisis quam ornare aliquam. Etiam cursus odio vitae dui dignissim, sed tempus lacus tincidunt et donec sapien velit, rhoncus eu nulla a, molestie tempus mi maecenas sagittis ornare.
          Pellentesque sapien mi, tincidunt nec magna vitae, volutpat elementum odioni lorem Aliquam tempor massa vitae augue mattis tempor id in ante ut augue erat, luctus eil.
        </p>
      </div>

      <div class="brand-section__container--5">
        <img class="grid-img" src="../assets/product3.jpg" alt="">
      </div>
      <div class="brand-section__container--6">
        <h4>ETHICAL TRADING</h4>
        <h6>WE OVERSEE THE WORKING CONDITIONS OF THE PEOPLE IN THE SUPPLY CHAIN</h6>
        <p>
          Nullam dapibus consectetur neque, faucibus porttitor purus iaculis sed. Aenean eras dapibus augue, eget dignissim dui maecenas et rhoncus mim, vel semper arcu lorem
          Pellentesque congue justo esteir pellentesque aliquet massa eget posuere tincidunt. Cras viverra ullamcorper nunc accumsan hendrerit.
        </p>
      </div>

      <div class="brand-section__container--7">
        <img class="awardImg" src="../assets/award1.png" alt="award image">
        <img class="awardImg" src="../assets/award1.png" alt="award image">
        <img class="awardImg" src="../assets/award1.png" alt="award image">
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
      TitleOne: 'THE BRAND',
      TitleTwo: 'COMPANY SLOGAN GOES HERE',
    }
  }
}
</script>


<style scoped lang="scss">

  @import "../styles/utilities/mixins.scss";
  @import "../styles/utilities/vars.scss";

  .brand-section {
    margin: auto;
    width: $width-medium;
    @include grid(0px, 25px, auto);
    padding: 50px 20px 100px 20px;

    @include media-query(small) {
      @include flexcolumn-cv;
      width: $width-small;
      padding: 50px 0px 100px 0px;
    }

      .brand-section__container--1 {
        height: 400px;
        @include grid-item-position(1, 7, 1, 5);
        margin-bottom: 50px;

        @include media-query(small) {
          margin-bottom: 10px;
        }
      }

      .brand-section__container--2 {
        @include grid-item-position(7, -1, 2, 3);
        margin-bottom: 50px;

        @include media-query(small) {
          padding: 0px 10px 0px 10px;
        }
      }

      .brand-section__container--3 {
        height: 400px;
        @include grid-item-position(1, 7, 5, 10);
        margin-bottom: 20px;

        @include media-query(small) {
          margin-bottom: 10px;
        }
      }

      .brand-section__container--4 {
        @include grid-item-position(1, 7, 10, 12);

        @include media-query(small) {
          margin-bottom: 50px;
          padding: 0px 10px 0px 10px;
        }
      }

      .brand-section__container--5 {
        height: 400px;
        @include grid-item-position(7, -1, 3, 8);
        margin-bottom: 20px;

        @include media-query(small) {
          margin-bottom: 10px;
        }
      }

      .brand-section__container--6 {
        @include grid-item-position(7, -1, 8, 10);

        @include media-query(small) {
          padding: 0px 10px 0px 10px;
        }
      }

      .brand-section__container--7 {
        @include grid-item-position(7, -1, 10, 12);
        @include flexrow-sb;
        margin-top: 50px;

        @include media-query(small) {
          flex-wrap: wrap;
          padding: 0px 10px 0px 10px;
        }

          .awardImg {
            height: 100px;

            @include media-query(small) {
              height: 100px;
              margin-bottom: 20px;

              &:last-child {
                margin: auto;
              }
            }
          }
      }

      .grid-img {
        object-fit: cover;
        height: 100%;
        width: 100%;
      }
}

</style>
