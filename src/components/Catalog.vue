<script>
import Filters from './Filters.vue'
import ProductsList from './ProductsList.vue'

export default {
    name: 'Catalog',
    components: {
        Filters,
        ProductsList
    },
    props: {},

    data() {
        return {
            filterId: Number,
        };
    },
    methods: {
        setFilter(id) {
            this.filterId = id;
        },
        handleBuy(product) {
            this.$emit("handle-buy", product)
        },
    },
};
</script>

<template>
    <section class="catalog">
        <Filters @set-filter="setFilter"/>
        <ProductsList :brand="filterId" @handle-buy="handleBuy"/>
    </section>
</template>

<style scoped>
.catalog {
    display: flex;
    flex-direction: row;
    padding: 20px 0 20px 0;
}
</style>
