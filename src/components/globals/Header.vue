<template>
    <header class="header">
        <div class="overlay">
            <h1 class="headline big">{{HeadlineOne}}</h1>
            <h2 class="headline small">{{HeadlineTwo}}</h2>
        </div>
    </header> 
</template>

<script>
export default {
    name: 'Header',
    props: ['HeadlineOne', 'HeadlineTwo']
}
</script>


<style scoped lang="scss">

.header {
    background-image: url('../../assets/bannerBg.jpg');
    background-position: center;
    background-repeat: no-repeat;
    height: 450px;

    .overlay {
        background-color: rgba(97, 97, 97, 0.8);
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        .headline {
            color: #ffffff;
            font-family: 'Montserrat', sans-serif;
            white-space: nowrap;
        }

        .big {
            font-size: 4em;

      @media only screen and (min-width : 320px) and (max-width : 480px) {
          font-size: 2em;
      }
        }

        .small {
            font-size: 2em;
            margin-top: 20px;

                  @media only screen and (min-width : 320px) and (max-width : 480px) {
          font-size: 1em;
      }
        }
    }
}

</style>
