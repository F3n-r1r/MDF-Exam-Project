<template>
    <section class="products-section">

        <hr>
    
        <div class="products-section__tabs scrollbar">
            <a v-on:click="activetab=1" v-bind:class="[ activetab === 1 ? 'active' : '' ]">POPULAR</a>
            <a v-on:click="activetab=2" v-bind:class="[ activetab === 2 ? 'active' : '' ]">NEW ARRIVALS</a>
            <a v-on:click="activetab=3" v-bind:class="[ activetab === 3 ? 'active' : '' ]">BEST SELLERS</a>
            <a v-on:click="activetab=4" v-bind:class="[ activetab === 4 ? 'active' : '' ]">SPECIAL OFFERS</a>
            <a v-on:click="activetab=5" v-bind:class="[ activetab === 5 ? 'active' : '' ]">COMING SOON</a>
        </div>

        <div class="content">

            <div class="content-container" v-for="data in filter(activetab)" :key="data.id" v-bind:class="data.class">
                <div class="test">
                    <div class="img-container" v-bind:class="data.class">
                        <img class="product-img" v-bind:src="require('@/assets/' + data.img)" v-bind:alt="data.imgAlt">
                    </div>
                    <div class="product-info">
                        Hoveered
                    </div>
                </div>
            </div>

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
                    img: 'product1.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small'
                },
                {
                    id: 1, 
                    img: 'product2.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small'
                },
                                {
                    id: 1, 
                    img: 'product3.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'big'
                },
                {
                    id: 1, 
                    img: 'product4.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'big'
                },
                {
                    id: 1, 
                    img: 'product5.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small'
                },
                {
                    id: 1, 
                    img: 'product6.jpg', 
                    imgAlt: 'Black Long Sleeved Sweatshirt',
                    class: 'small'
                },

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
.test {
    position: absolute;
    width: 100%;
}


.products-section {
      margin: 50px auto 50px auto;
      display: flex;
      flex-direction: column;
      min-width: 1024px;
      max-width: 1440px;
      padding: 0px 40px 0px 40px;
      
    @media only screen and (min-width : 320px) and (max-width : 480px) {
      min-width: 320px;
    }

    .products-section__tabs {
        margin: 40px 0px 40px 0px;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
            overflow: hidden;
            overflow-x: scroll;
        }

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

                .scrollbar::-webkit-scrollbar-track
{
 
    box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	-webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	border-radius: 10px;
	background-color: #F5F5F5;
}

.scrollbar::-webkit-scrollbar
{
	width: 12px;
	background-color: #F5F5F5;
}

.scrollbar::-webkit-scrollbar-thumb
{
	border-radius: 10px;
    box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	-webkit-box-shadow: inset 0 0 6px rgba(0,0,0,.3);
	background-color: #00c8c8;
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

.content-container {
    position: relative;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    background-color: #f8f8f8;
    width: 100%;
    cursor: pointer;

    &:hover {
       box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }

   
    &:hover .product-info{
        display: flex;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
}



.img-container {
    position: relative;
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    background-color: #f8f8f8;
    width: 100%;

}

    .product-info {
        position: absolute;
        width: 100%;
        display: none;
        background-color: #ffffff;
        flex-direction: column;
        align-items: center;
        z-index: 999;
    }

.big {
    height: 500px;
    grid-column: span 6;
    grid-row: span 2;

    @media only screen and (min-width : 320px) and (max-width : 480px) {
      grid-column: span 12;
      grid-row: span 2;
      height: 300px;
          width: 100%;
    }
}

.small {
    height: 300px;
      grid-column: span 3;
      grid-row: span 1;

            @media only screen and (min-width : 320px) and (max-width : 480px) {
      grid-column: span 12;
      grid-row: span 1;
      height: 300px;
    }
}

.product-img {
    height: 100%;
    object-fit: cover;
    
    @media only screen and (min-width : 320px) and (max-width : 480px) {
      width: 100%;
    }
}











</style>
