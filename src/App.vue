<script setup>
const products = ['역삼동원룸', '천호동원룸', '마포구원룸'];

const menus = ['Home', 'Product', 'About'];
</script>

<template>
  <ul>
    <li v-for="(menu, idx) in menus" :key="idx">{{ menu }}</li>
  </ul>
  <img src="/vite.svg" class="logo" alt="Vite logo" />
  <div></div>
  {{ products[0] }}
  <p>50만원</p>
  {{ products[1] }}
  <p>50만원</p>
  {{ products[2] }}
  <p>50만원</p>
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
