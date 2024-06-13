<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Catalog from './components/Catalog.vue'
</script>

<template>
  <header>
    <img alt="Astrio" class="logo" src="./assets/images/logo.png" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <Catalog />
  </main>
</template>

<style scoped>
.logo {
  display: block;
  margin: 0 auto 2rem;
}

header {
  display: flex;
  justify-content: space-between;
}

.logo {
  margin: 0 2rem 0 0;
}
</style>
