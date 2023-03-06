<script setup>
import { ref } from 'vue';

const products = ['역삼동원룸', '천호동원룸', '마포구원룸'];
const price = ['50만원', '60만원', '70만원'];

const menus = ['Home', 'Product', 'About'];

const count = ref([0, 0, 0]);
const onClick = () => {
  count.value++;
};
</script>

<template>
  <ul>
    <li v-for="(menu, idx) in menus" :key="idx">{{ menu }}</li>
  </ul>
  <img src="/vite.svg" class="logo" alt="Vite logo" />
  <div>
    <strong style="display: block">{{ products[0] }}</strong>
    <p>{{ price[0] }}</p>
    <button @click="count[0]++">허위매물 신고 버튼</button> <span>신고수 : {{ count[0] }}</span>
  </div>
  <div>
    <strong style="display: block">{{ products[1] }}</strong>
    <p>{{ price[1] }}</p>
    <button @click="count[1]++">허위매물 신고 버튼</button> <span>신고수 : {{ count[1] }}</span>
  </div>
  <div>
    <strong style="display: block">{{ products[2] }}</strong>
    <p>{{ price[2] }}</p>
    <button @click="count[2]++">허위매물 신고 버튼</button> <span>신고수 : {{ count[2] }}</span>
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
