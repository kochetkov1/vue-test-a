<script setup>
import Filters from './Filters.vue'
import ProductsList from './ProductsList.vue'

let filterId = null;

function setFilter(id) {
  console.log('id', id);
  filterId = id;
  console.log('filterId', filterId);
}
</script>

<template>
  <section class="catalog">
    <Filters @set-filter="setFilter" />
    <ProductsList :brand="filterId" />
  </section>
</template>

<style scoped>
.catalog {
  display: flex;
  flex-direction: row;
  padding: 20px 0 20px 0;
}
</style>
