<script>
import brands from '../assets/brands.json'

export default {
    name: 'Filters',
    data() {
        return {
            initBrands: []
        };
    },
    mounted() {
        this.initBrands = brands;
    },
    methods: {
        setId(id) {
            this.$emit('set-filter', id)
        },
    },
};
</script>

<template>
    <div class="filters">
        <ul class="filters__list">
            <li v-for="brand in initBrands" :key="brand.id" class="filters__list-item" @click="setId(brand.id)">&#8250;
                {{ brand.title }}
            </li>
            <li class="filters__list-item" @click="setId(null)">&#8250; All brands</li>
        </ul>
    </div>
</template>

<style scoped lang="scss">
.filters {
    display: flex;
    max-width: 200px;
    min-width: 150px;
    width: 100%;
    padding: 10px;

    &__list {
        list-style: none;
    }

    &__list-item {
        cursor: pointer;
    }
}
</style>
