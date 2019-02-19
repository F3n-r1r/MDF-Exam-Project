<template>
    <section class="products-section">

        <hr>
    
        <div class="products-section__tabs">
            <a v-on:click="activetab=1" v-bind:class="[ activetab === 1 ? 'active' : '' ]">POPULAR</a>
            <a v-on:click="activetab=2" v-bind:class="[ activetab === 2 ? 'active' : '' ]">NEW ARRIVALS</a>
            <a v-on:click="activetab=3" v-bind:class="[ activetab === 3 ? 'active' : '' ]">BEST SELLERS</a>
            <a v-on:click="activetab=4" v-bind:class="[ activetab === 4 ? 'active' : '' ]">SPECIAL OFFERS</a>
            <a v-on:click="activetab=5" v-bind:class="[ activetab === 5 ? 'active' : '' ]">COMING SOON</a>
        </div>

        <div class="content"  v-for="data in filter(activetab)" :key="data.id">
            <div class="img-container small">
                <img class="product-img" v-bind:src="require('@/assets/' + data.imgOne)" v-bind:alt="data.imgOneAlt">
            </div>
            <div class="img-container small">
                <img class="product-img" v-bind:src="require('@/assets/' + data.imgTwo)" v-bind:alt="data.imgTwoAlt">
            </div>
            <div class="img-container big">
                <img class="product-img" v-bind:src="require('@/assets/' + data.imgThree)" v-bind:alt="data.imgThreeAlt">
            </div>
            <div class="img-container big">
                <img class="product-img" v-bind:src="require('@/assets/' + data.imgFour)" v-bind:alt="data.imgFourAlt">
            </div>
            <div class="img-container small">
                <img class="product-img" v-bind:src="require('@/assets/' + data.imgFive)" v-bind:alt="data.imgFiveAlt">
            </div>
            <div class="img-container small">
                <img class="product-img" v-bind:src="require('@/assets/' + data.imgSix)" v-bind:alt="data.imgSixAlt">
            </div>

            <!-- Alternate solution for making the tabbed content -->
            <!--<div v-if="activetab === 2" class="tabcontent"></div>-->
        </div>
    
        <hr>

    </section>
</template>


<script>

export default {
    name: 'Products',
    data: function() {
        return {
    
            activetab: 1,
            // Static tab content
            tabs: [
                {
                    id: 1, 
                    imgOne: 'product1.jpg', 
                    imgOneAlt: 'Black Long Sleeved Sweatshirt',
                    imgTwo: 'product2.jpg', 
                    imgTwoAlt: 'Black Long Sleeved Sweatshirt',
                    imgThree: 'product3.jpg', 
                    imgThreeAlt: 'Black Long Sleeved Sweatshirt',
                    imgFour: 'product4.jpg', 
                    imgFourAlt: 'Black Long Sleeved Sweatshirt',
                    imgFive: 'product5.jpg', 
                    imgFiveAlt: 'Black Long Sleeved Sweatshirt',
                    imgSix: 'product6.jpg', 
                    imgSixAlt: 'Black Long Sleeved Sweatshirt',
                },
                {
                    id: 2, 
                    imgOne: 'lookbookMan.png', 
                    imgOneAlt: 'Black Long Sleeved Sweatshirt',
                    imgTwo: 'product2.jpg', 
                    imgTwoAlt: 'Black Long Sleeved Sweatshirt',
                    imgThree: 'product3.jpg', 
                    imgThreeAlt: 'Black Long Sleeved Sweatshirt',
                    imgFour: 'product4.jpg', 
                    imgFourAlt: 'Black Long Sleeved Sweatshirt',
                    imgFive: 'product5.jpg', 
                    imgFiveAlt: 'Black Long Sleeved Sweatshirt',
                    imgSix: 'product6.jpg', 
                    imgSixAlt: 'Black Long Sleeved Sweatshirt',
                }
            ],
        }
    },

    methods: {
        filter: function(activetab) {
            return this.tabs.filter(function(tab) {
                return tab.id === activetab
            })
        }
    }

}
</script>


<style scoped lang="scss">

.products-section {
      margin: 50px auto 50px auto;
      display: flex;
      flex-direction: column;
      max-width: 1440px;
      padding: 0px 40px 0px 40px;

    .products-section__tabs {
        margin: 40px 0px 40px 0px;

        & a{
            cursor: pointer;
            padding: 12px 24px;
            white-space: nowrap;

            &:first-child {
                padding-left: 0px;
            }

            &:hover {
                color: #00c8c8;
            }

            &.active {
                color: #00c8c8;
                cursor: default;
            }
        }
    }
}

.content {
    display: grid;
    grid-gap: 20px;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: auto;
    grid-auto-flow: dense;
    margin: 0px 0px 40px 0px;
}

.img-container {
    display: flex;
    justify-content: center;
    align-items: center;
}

.big {
    grid-column: span 6;
    grid-row: span 8;
}

.small {
    grid-column: span 3;
    grid-row: span 4;
}

.product-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}











</style>
