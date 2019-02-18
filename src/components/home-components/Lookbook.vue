<template>
    <section class="lookbook-section">

      <div class="lookbook-section__container">
        <img class="lookbook-quickView__element__img" src="@/assets/lookbookMan.png" alt="A well dressed man">
        <div class="lookbook-quickView__element__info">
          <h3 class="look-quickView-heading--bold">MEN'S</h3>
          <h3 class="look-quickView-heading">LOOKBOOK</h3>
          <p class="look-quickView-text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia repudiandae nam aliquid magnam provident.</p>
          <button class="look-quickView-btn">VIEW NOW</button>
        </div>
      </div>

      <div class="lookbook-section__container">
        <img class="lookbook-quickView__element__img" src="@/assets/lookbookMan.png" alt="A well dressed man">
        <div class="lookbook-quickView__element__info">
          <h3 class="look-quickView-heading--bold">WOMEN'S</h3>
          <h3 class="look-quickView-heading">LOOKBOOK</h3>
          <p class="look-quickView-text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia repudiandae nam aliquid magnam provident.</p>
          <button class="look-quickView-btn">VIEW NOW</button>
        </div>
      </div>

      <div class="lookbook-section__container">
        <img class="lookbook-quickView__element__img" src="@/assets/lookbookMan.png" alt="A well dressed man">
        <div class="lookbook-quickView__element__info">
          <h3 class="look-quickView-heading--bold">YOUR</h3>
          <h3 class="look-quickView-heading">LOOKBOOK</h3>
          <p class="look-quickView-text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Mollitia repudiandae nam aliquid magnam provident.</p>
          <button class="look-quickView-btn">VIEW NOW</button>
        </div>
      </div>

    </section>
</template>


<script>
export default {
    name: 'Lookbook',
}
</script>


<style scoped lang="scss">

.lookbook-section {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
    grid-gap: 20px;
    margin: 50px 0px 50px 0px;
    justify-content: space-between center;
            
    @media only screen and (min-width : 320px) and (max-width : 480px) {
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    }

    .lookbook-section__container {
        background-color: #f8f8f8;
        padding: 50px 20px 0px 20px;
        display: flex;
        justify-content: space-around;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
            padding: 50px 20px 50px 20px;
        }


        .lookbook-quickView__element__img {
            height: 400px;
            margin-top: 0;

            @media only screen and (min-width : 769px) and (max-width : 1024px) {
                height: 300px;
            }
            
            @media only screen and (min-width : 481px) and (max-width : 768px) {
               
            }

            @media only screen and (min-width : 320px) and (max-width : 480px) {
                display: none;
            }
        }

        .lookbook-quickView__element__info {
            display: flex;
            flex-direction: column;



            .look-quickView-heading--bold {
                margin-left: auto;
                font-size: 3em;
                color: #575153;
                font-family: 'Roboto', sans-serif;


            
        @media only screen and (min-width : 320px) and (max-width : 480px) {
            margin: auto;
        }
            }

            .look-quickView-heading {
                margin-left: auto;
                font-size: 3em;
                color: #575153;
                font-family: 'Montserrat', sans-serif;
                        @media only screen and (min-width : 320px) and (max-width : 480px) {
            margin: auto;
        }
            }

            .look-quickView-text {
                text-align: right;
                max-width: 400px;
                margin-top: 30px;
                        @media only screen and (min-width : 320px) and (max-width : 480px) {
            text-align: center;
        }
            }

            .look-quickView-btn {
                margin-left: auto;
                margin-top: 40px;
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

                @media only screen and (min-width : 320px) and (max-width : 480px) {
                    margin: auto;
                    margin-top: 40px;
                }
            }
        }
    }
}

</style>
