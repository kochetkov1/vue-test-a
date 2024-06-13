<script setup>
import ProductCard from './ProductCard.vue'
import products from '../assets/products.json'
import { onMounted, watchEffect, toRefs, watch, ref } from 'vue';

const props = defineProps({
  brand: Number
})

let initProducts = products;

function test1() {
  console.log('props.brand', props.brand);
}

// onMounted(() => {
// console.log('brandId', props.brandId);
// if (props.brandId) {
//   products = products.filter(item => item.brand = props.brandId);
// }
// })

// const selected = ref(props.brandId)

watchEffect(() => {
  const parse = toRefs(props.brand);
  console.log('props.brandId', props.brand);
  if (props.brand) {
    initProducts = products.filter(item => item.brand === props.brand);
  }
});

// const selected = ref(props.brandId)

// watch(selected, (selection, prevSelection) => {
//   if (props.brandId) {
//     products = products.filter(item => item.brand = props.brandId);
//   }
//   console.log('brandId', props.brandId);
// })
</script>

<template>
  <button @click="test1()">432424242342</button>
  <div class="products-list">
    <ProductCard v-for="product in initProducts" :key="product.id" :product="product" />
  </div>
</template>

<style scoped>
.products-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  width: 100%;
  padding: 10px;
}
</style>
