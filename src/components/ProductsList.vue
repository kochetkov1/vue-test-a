<script>
import ProductCard from './ProductCard.vue'
import products from '../assets/products.json'

export default {
    name: 'ProductsList',
    components: {
        ProductCard
    },
    props: {
        brand: {
            type: Number,
            default: null
        },
    },

    data() {
        return {
            initProducts: [],
        };
    },

    mounted() {
        this.initProducts = products;
    },
    methods: {
        handleBuy(product) {
            this.$emit('handle-buy', product)
        },
    },

    watch: {
        brand: {
            handler(value) {
                if (value) {
                    this.initProducts = products.filter(item => {
                        if (item.brand === value) return item;
                    });
                } else {
                    this.initProducts = products;
                }
            }
        }
    }
};
</script>

<template>
    <div v-if="this.initProducts.length" class="products-list__main">
        <ProductCard v-for="product in this.initProducts" :key="product.id" :product="product" @handle-buy="handleBuy" />
    </div>
    <p v-else class="products-list__empty">
        Ничего не найдено
    </p>
</template>

<style scoped lang="scss">
.products-list {
    &__main {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
        width: 100%;
        padding: 10px;
    }

    &__empty {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 100%;
    }
}
</style>
