<script>
import Cart from './components/Cart.vue'
import Catalog from './components/Catalog.vue'

export default {
    name: 'App',
    components: {
        Cart,
        Catalog
    },
    data() {
        return {
            purchasedProducts: [],
        };
    },
    methods: {
        addProduct(product) {
            this.purchasedProducts.push(product);
        }
    },
};
</script>

<template>
    <header>
        <a href="/">
            <img alt="Astrio" class="app__logo" src="./assets/images/logo.png" />
        </a>

        <div class="wrapper">
            <Cart :purchased-products="purchasedProducts" />
        </div>
    </header>

    <main>
        <Catalog @handle-buy="addProduct" />
    </main>
</template>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
}

.app__logo {
    display: block;
    margin: 0 2rem 0 0;
    height: 34px;
}
</style>
