<script>
export default {
    name: 'ProductCard',
    props: {
        product: {
            type: Object,
            default: null
        },
    },

    data() {
        return {};
    },
    methods: {
        handleBuy(product) {
            this.$emit("handle-buy", product)
        },
    },
};
</script>

<template>
    <article class="product-card">
        <img :src="`${'src/assets' + product.image}`" :alt="product.title" class="products-card__image">
        <div class="product-card__info-block">
            <span class="product-card__price">{{ product.regular_price.value }} {{
                    product.regular_price.currency
                }}</span>
            <h3 class="product-card__title">{{ product.title }}</h3>
            <span class="product-card__brand">Brand: {{ product.brand }}</span>
        </div>
        <button @click="handleBuy(product)" class="product-card__buy-button">Купить</button>
    </article>
</template>

<style scoped>
.product-card {
    display: flex;
    flex-direction: column;
    gap: 5px;
    max-width: 200px;
    border: 1px solid #f3f6f4;
    border-radius: 10px;
    padding: 10px;
}

.product-card:hover {
    border-color: #e4e7e5;
}

.product-card__info-block {
    display: flex;
    flex-direction: column;
}

.product-card__buy-button {
    border: none;
    border-radius: 18px;
    background-color: #ee6603;
    width: 100%;
    height: 36px;
    color: #f3f6f4;
    font-weight: 700;
    font-size: 16px;
    cursor: pointer;
}

.product-card__buy-button:hover {
    background-color: #ff5100;
}

.product-card__brand {
    color: #c4c5c4;
}

.product-card__price {
    color: #F81155;
    font-weight: 700;
}

.products-card__image {
    max-width: 200px;
}
</style>
