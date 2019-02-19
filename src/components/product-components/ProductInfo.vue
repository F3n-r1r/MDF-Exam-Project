<template>
    <div class="info-container">
        <h3>AVE CLASSIC SWEATSHIRT</h3>

        <div class="info-container__social">
            <div class="reviews">
                <div class="reviews__stars">
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                    <i class="fas fa-star"></i>
                </div>
                <p class="social-text link">
                    3 Reviews(s)
                </p>
                <div class="vl"></div>
                <p class="social-text link">
                    Add a review
                </p>
                <div class="vl"></div>
            </div>
            <div class="share">
                <p class="social-text">
                    Share:
                </p>
                <div class="share__icons">
                    <i class="icon fab fa-facebook-f"></i>
                    <i class="icon fab fa-twitter"></i>
                    <i class="icon fab fa-google-plus-g"></i>
                    <i class="icon fab fa-pinterest-p"></i>
                    <i class="icon fab fa-instagram"></i>
                    <i class="icon far fa-envelope"></i>
                </div>
            </div>
        </div>

        <div class="info-container__pricing">
            <p class="price price--line">
                107
            </p>
            <p class="price">
                89.99
            </p>
        </div>

        <div class="info-container__notes">
            <p class="text">
                AVAILABILITY: <span class="text__value">In stock</span>
            </p>
            <p class="text">
                PRODUCT CODE: <span class="text__value">#499577</span>
            </p>
            <p class="text">
                TAGS: <span class="text__value text__value--green">Classic, Casual, V-neck, Loose</span>
            </p>
        </div>

        <div class="info-container__description">
            <p class="text">
                Donec sem lorem laoreet tempor un risus vitae, rutrum sodales nibh suspendisse est congue metus nunc, id viverra elit loreti rhoncus quis consecteur es. Donec pulvinar tempor lorem a pretium justo interdum.
            </p>
            <ul class="highlighted-list">
                <li class="highlighted-list__item">
                    Elasticated cuffs
                </li>
                <li class="highlighted-list__item">
                    Casual fit
                </li>
                <li class="highlighted-list__item">
                    100% Cotton
                </li>
                <li class="highlighted-list__item">
                    Free shipping with 4 days delivery
                </li>
            </ul>
        </div>

        <div class="info-container__selection">
            <div class="option-container">
                <label class="selector-label" for="color">COLOUR</label>
                <select class="selector-drpdown" name="color" id="color">
                    <option value="" disabled selected>Select Colour</option>
                    <option value="Black">Black</option>
                    <option value="Grey">Grey</option>
                    <option value="Brown">Brown</option>
                </select>
            </div>
            <div class="option-container">
                <label class="selector-label" for="size">SIZE</label>
                <select class="selector-drpdown" name="size" id="size">
                    <option value="" disabled selected>Select Size</option>
                    <option value="Black">Small</option>
                    <option value="Grey">Medium</option>
                    <option value="Brown">Large</option>
                </select>
            </div>
            <div class="option-container">
                <label class="selector-label" for="qty">QTY</label>
                <input class="selector-qty" type="number" min="1" step="1" value="1" name="qty" id="qty">
                <div class="spin-container">
                    <button class="spin spin__up">O</button>
                    <button class="spin spin__down">D</button>
                </div>
            </div>
        </div>

        <div class="add-button-container">
            <button class="btn"><i class="icon fas fa-shopping-cart"></i>ADD TO CARD</button>
            <button class="btn"><i class="icon far fa-heart"></i>ADD TO LOOKBOOK</button>
            <button class="btn btn--no-border"><i class="icon fas fa-compress-arrows-alt"></i>ADD TO COMPARE</button>
        </div>
    </div>

</template>


<script>

export default {
    name: 'ProductInfo',
    data: function() {
        return {
    
    }
    }
}
</script>


<style scoped lang="scss">

    .info-container {
        position: relative;
        display: flex;
        justify-content: space-between;
        flex-direction: column;
        grid-column: span 6;
        white-space: nowrap;
        font-size: 0.8em;

        .social-text {
            margin: 0px 10px 0px 10px;
        }

        .info-container__social {
            display: flex;
            margin: 15px 0px 15px 0px;

            .reviews {
                display: flex;
                width: 100%;
                justify-content: space-between;
                align-items: center;

                .vl {
                border-left: 1px solid #8c8c8c;
                height: 100%;
                }

                .reviews__stars {
                    color: #ded3aa;

                    :last-child {
                        color: #dfdfde;
                    }
                }

                .link {
                    cursor: pointer;

                    &:hover {
                        color: #33d3d3;
                    }
                }
            }

            .share {
                display: flex;
                width: 100%;
                justify-content: space-between;
                align-items: center;

                .share__icons {
                    display: flex;
                    width: 100%;
                    justify-content: space-between;

                    .icon {
                        color: #8c8c8c;

                        &:hover {
                            color: #33d3d3;
                            cursor: pointer;
                        }
                    }
                }
            }
        }

        .info-container__pricing {
            display: flex;

            .price {
                margin-right: 15px;
                font-size: 2em;
                color: #9a9a9a;

                &:before {
                    content: "\00a3";
                    font-size: 0.6em;
                    vertical-align: top;
                    
                }
            }

            .price--line {
                text-decoration: line-through;
            }
        }

        .info-container__notes {
            margin: 15px 0px 15px 0px;

            .text {
                font-weight: bold;
                margin-top: 15px;

                .text__value {
                    font-weight:normal;
                }

                .text__value--green {
                    color: #33d3d3;
                }
            }
        }

        .info-container__description {
            color: #a5a3a3;
            margin-bottom: 30px;

            .text {
                white-space: pre-line;
                line-height: 1.6;
            }

            .highlighted-list {
                list-style-position: inside;
                line-height: 1.6;
                margin-top: 10px;
            }
        }

        .info-container__selection {
            display: flex;
            margin-bottom: 30px;

            .option-container {
                display: flex;
                flex-direction: column;
                position: relative;

                .selector-label {
                    margin-bottom: 5px;
                    font-family: 'Roboto', sans-serif;
                    font-weight: bold;
                    color: #575153;
                }

                .selector-drpdown {
                    padding: 10px;
                    margin-right: 25px;
                    font-family: 'Montserrat', sans-serif;
                    color: #a6a6a6;
                    border-color: #e7e7e7;

                    &:focus {
                        outline: none;
                    }
                }

                .selector-qty {
                    padding: 11px;
                    width: 50px;
                    font-family: 'Montserrat', sans-serif;
                    color: #a6a6a6;
                    border:1px solid #e7e7e7;
                    -webkit-appearance: textfield;
                    -moz-appearance: textfield;
                    appearance: textfield;

                    &:focus {
                        outline: none;
                    }

                    &::-webkit-inner-spin-button, &::-webkit-outer-spin-button {
                        -webkit-appearance: none; 
                        margin: 0;
                    }                       
                }
            }
        }

        .add-button-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;


            .btn {
                padding: 10px 35px 10px 35px;
                margin-top: 15px;
                font-size: 1.2em;
                font-family: 'Montserrat', sans-serif;
                background-color: transparent;
                color: #454647;
                white-space: nowrap;
                font-weight: bold;
                border: 2px solid #737373;
                cursor: pointer;

                &:hover {
                    background-color: #333333;
                    color: #ffffff;
                    border-color: #333333;
                }

                .icon {
                    margin-right: 10px;
                }
            }

            .btn--no-border {
                border-style: none;
                padding: 10px 15px 10px 0px;

                &:hover {
                    background-color: transparent;
                    color: #454647;
                }
            }
        }
    }
</style>
