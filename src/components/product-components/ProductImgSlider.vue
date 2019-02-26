<template>
    <div class="carousel-container">
        <div class="img-container">
            <img class="img-container__img" v-bind:src="require('@/assets/' + currentImage)" alt="">
            <div class="img-container__actions-container">
                <span @click="prevImage" class="actions-container__action">
                    <i class="action__icon fas fa-chevron-left"></i>
                </span>
                <span @click="nextImage" class="actions-container__action">
                    <i class="action__icon fas fa-chevron-right"></i>
                </span>
            </div>
        </div>
    </div>
</template>


<script>

export default {
    name: 'ProductImgSlider',
    data: function() {
        return {
            // Array that hold all the images (In real app it should be populated by making a call to an api)
            images: [
                {
                    id: '1',
                    img: 'productPageImg.jpg'
                },
                {
                    id: '2',
                    img: 'product1.jpg'
                },
                {
                    id: '3',
                    img: 'product2.jpg'
                },
                {
                    id: '4',
                    img: 'product3.jpg'
                }
            ],
            // Index of the active image in the 'images' array (First to show is at index 0)
            activeImage: 0
        }
    },
    computed: {
        // CurrentImage gets called whenever the state of activeImage changes
        currentImage() {
            // Takes the array & finds the object at index 'activeImage' & returns the value of 'img' in that object
            return this.images[this.activeImage].img;
        }
    },
    methods: {
        // Go forward on the images array 
        // or go at the first image if you can't go forward
        nextImage() {
            var active = this.activeImage + 1;
            if(active >= this.images.length) {
                active = 0;
            }
            this.activateImage(active);
        },
        // Go backwards on the images array 
        // or go at the last image
        prevImage() {
            var active = this.activeImage - 1;
            if(active < 0) {
                active = this.images.length - 1;
            }
            this.activateImage(active);
        },
        // Changes the state of the activeImage
        activateImage(imageIndex) {
            this.activeImage = imageIndex;
        }
    }
}
</script>


<style scoped lang="scss">

    .carousel-container {
        grid-column: span 6;
        position: relative;
        user-select: none;

        @media only screen and (min-width : 320px) and (max-width : 480px) {
            max-width: 300px;
            min-height: 300px;
        }

        .img-container {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            overflow: hidden;

            @media only screen and (min-width : 320px) and (max-width : 480px) {
                position: relative;
                height: 400px;
            }

            .img-container__img {
                position: relative;
                height: 100%;


                @media only screen and (min-width : 320px) and (max-width : 480px) {
                    object-fit: fill;
                }
            }

            .img-container__actions-container {
                font-size: 1.5em;
                position: absolute;
                top: 50%;
                width: 100%;
                display: flex;
                align-items: center;
                justify-content: space-between;
                color: #575153;

                .actions-container__action {
                    cursor: pointer;
                    padding: 8px;

                    &:hover {
                        color: #eee;
                        background-color: #00c8c8;
                    }

                    .action__icon {
                        font-size: 1.3em;
                    }
                }
            }
        }
    }

</style>
