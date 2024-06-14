<script>
export default {
    name: "Cart",
    props: {
        purchasedProducts: {
            type: Array,
            default: []
        },
    },
    data() {
        return {};
    },
    methods: {},
}
</script>

<template>
    <div class="cart">
        <img class="cart__image" src="../assets/images/cart-large.svg" alt="">
        <span v-if="purchasedProducts.length" class="cart__counter">{{ purchasedProducts.length }}</span>
    </div>

</template>

<style scoped>
.cart {
    cursor: pointer;
    position: relative;
}

.cart__image {
    height: 40px;
}

.cart__counter {
    position: absolute;
    top: -10px;
    right: -10px;
    height: 25px;
    border-radius: 10px;
    background-color: #ee6603;
    color: #f3f6f4;
    padding: 0 5px;
}
</style>
