<template>
    <div>
        <div v-if="isLoading">
            <Loader />
        </div>
        <div v-else>
            <div v-if="product?.singleProduct?.category === 'women\'s clothing' || product?.singleProduct?.category === 'men\'s clothing'">
                <div :class="product?.singleProduct?.category === 'women\'s clothing' ? 'bg-header-womens-clothing' : 'bg-header-mens-clothing'"></div>
                
                <div :class="product?.singleProduct?.category === 'women\'s clothing' ? 'womens-clothing-container' : 'mens-clothing-container'">
                    <div>
                        <img class="img-product" :src="product?.singleProduct?.image" alt="men">
                    </div>
                    <div>
                        <h1>{{ product?.singleProduct?.title }}</h1>
                        <div class="title-and-rating-container">
                            <h2 class="title">{{ product?.singleProduct?.category }}</h2>
                            <div class="rating-container">
                                <h2>{{ product?.singleProduct?.rating?.rate }}/{{ product?.singleProduct?.rating?.count }}</h2>
                                <div v-if="product?.singleProduct?.category === 'women\'s clothing'">
                                    <div v-if="product?.singleProduct?.rating?.rate <= 1" class="star-container">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingwhite">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingwhite">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingwhite">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingviolet">
                                    </div>
                                    <div v-else-if="product?.singleProduct?.rating?.rate <= 2" class="star-container">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingwhite">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingwhite">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingviolet">
                                    </div>
                                    <div v-else-if="product?.singleProduct?.rating?.rate <= 3" class="star-container">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingwhite">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingviolet">
                                    </div>
                                    <div v-else-if="product?.singleProduct?.rating?.rate <= 4" class="star-container">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingwhite.png" alt="ratingviolet">
                                    </div>
                                    <div v-else class="star-container">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                        <img src="../assets/img/ratingviolet.png" alt="ratingviolet">
                                    </div>
                                </div>
                                <div v-if="product?.singleProduct?.category === 'men\'s clothing'">
                                    <div v-if="product?.singleProduct?.rating?.rate <= 1" class="star-container">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                    </div>
                                    <div v-else-if="product?.singleProduct?.rating?.rate <= 2" class="star-container">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                    </div>
                                    <div v-else-if="product?.singleProduct?.rating?.rate <= 3" class="star-container">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                    </div>
                                    <div v-else-if="product?.singleProduct?.rating?.rate <= 4" class="star-container">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingbluewhite.png" alt="ratingbluewhite">
                                    </div>
                                    <div v-else class="star-container">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                        <img src="../assets/img/ratingblue.png" alt="ratingblue">
                                    </div>
                                </div>
                            </div>
                        </div>

                        <div class="line"></div>

                        <p>{{ product?.singleProduct?.description }}</p>

                        <div class="line"></div>

                        <h3>${{ product?.singleProduct?.price }}</h3>

                        <div class="button-container">
                            <button class="buy-now">Buy Now</button>
                            <button class="next-product" @click="fetchNextProduct()">Next Product</button>
                        </div>
                    </div>
                </div>
            </div>
            <div v-else>
                <div class="bg-header-unavailable"></div>

                <div class="unavailable-container">
                    <div class="img-message-button-container">
                        <img src="../assets/img/sad-face.png" alt="sad-face">
                        <div class="message-button-container">
                            <p>This product is unavailable to show</p>
                            <button @click="fetchNextProduct()">Next Product</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Loader from './Loader.vue';

export default {
    name: 'Product',
    components: {
        Loader
    },
    data() {
        return {
            indexProduct: 0,
            product: {},
            length: 0,
            isLoading: false
        }
    },

    mounted() {
        this.fetchNextProduct();
    },

    methods: {
        // increment index product, if index product >= 20 is reset index product to 1
        increment() {
            if (this.indexProduct < 20) {
                this.indexProduct++;
            } else {
                this.indexProduct = 1;
            }
        },

        // fetch API Single Product By Index Product, Default start from index product 1, when load browser
        async fetchProduct() {
            try {
                let response = await fetch(`https://fakestoreapi.com/products/${this.indexProduct}`);
                if (!response.ok) {
                    throw new Error("Network response was not ok");
                }

                let responseJson = await response.json();
                return responseJson;
            } catch (error) {
                console.log(error.message);
            }
        },

        // Fecth API Single when click button Next products
        async fetchNextProduct() {
            this.isLoading = true;

            this.increment();

            let singleProduct = await this.fetchProduct();

            this.product = { singleProduct };

            this.length = Object.keys(this.product).length;

            this.isLoading = false;
            
            // console.log(this.length);
            // console.log(this.product.singleProduct);
        }
    }
}
</script>

<style>
    @import url("../assets/style.css");
</style>