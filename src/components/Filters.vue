<script setup>
import brands from '../assets/brands.json'

const emit = defineEmits(['setFilter'])

function setId(id) {
  emit('setFilter', id)
}
</script>

<template>
  <div class="filters">
    <ul class="filters__list">
      <li v-for="brand in brands" :key="brand.id" class="filters__list-item" @click="setId(brand.id)">&#8250; {{
        brand.title }}</li>
    </ul>
  </div>
</template>

<style scoped>
.filters {
  display: flex;
  max-width: 200px;
  min-width: 150px;
  width: 100%;
  padding: 10px;
}

.filters__list {
  list-style: none;
}

.filters__list-item {
  cursor: pointer;
}
</style>
