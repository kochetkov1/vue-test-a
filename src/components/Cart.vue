<script>
export default {
    name: 'Cart',
    props: {
        purchasedProducts: {
            type: Array,
            default: []
        },
    },
}
</script>

<template>
    <div class="cart">
        <img class="cart__image" src="../assets/images/cart-large.svg" alt="">
        <span v-if="purchasedProducts.length" class="cart__counter">{{ purchasedProducts.length }}</span>
    </div>
</template>

<style scoped lang="scss">
.cart {
    cursor: pointer;
    position: relative;

    &__image {
        height: 40px;
    }

    &__counter {
        position: absolute;
        top: -10px;
        right: -10px;
        height: 25px;
        border-radius: 10px;
        background-color: #ee6603;
        color: #f3f6f4;
        padding: 0 5px;
    }
}
</style>
