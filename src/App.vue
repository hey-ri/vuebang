<script setup>
import { ref } from 'vue';
import data from './data';

const menus = ['Home', 'Product', 'About'];
const product = data;

const count = ref([0, 0, 0]);
const onClick = () => {
  count.value++;
};

const isModal = ref(false);
</script>

<template>
  <ul>
    <li v-for="(menu, idx) in menus" :key="idx">{{ menu }}</li>
  </ul>

  <div class="black-bg" v-if="isModal === true">
    <div class="white-bg">
      <h3>상세 페이지</h3>
      <p>내용</p>
      <button @click="isModal = false">닫기</button>
    </div>
  </div>

  <div v-for="(data, index) in product" :key="index">
    <img :src="data.image" alt="사진" class="room-img" />

    <strong style="display: block" @click="isModal = true">{{ data.title }}</strong>
    <p>{{ data.price }}원</p>
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
.room-img {
  width: 100%;
  margin-top: 50px;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  left: 0;
  top: 0;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
