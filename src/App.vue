<script setup>
const products = ['역삼동원룸', '천호동원룸', '마포구원룸'];
const price = ['50만원', '60만원', '70만원'];

const menus = ['Home', 'Product', 'About'];
</script>

<template>
  <ul>
    <li v-for="(menu, idx) in menus" :key="idx">{{ menu }}</li>
  </ul>
  <img src="/vite.svg" class="logo" alt="Vite logo" />
  <div v-for="(product, index) in products" :key="index">
    <strong style="display: block">{{ product }}</strong>
    <p>{{ price[index] }}</p>
  </div>
</template>

<style scoped>
ul {
  display: flex;
  gap: 10px;
  justify-content: center;
}
li {
  list-style: none;
}
</style>
