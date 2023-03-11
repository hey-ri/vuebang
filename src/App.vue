<script setup>
import { ref } from 'vue';

const products = ['역삼동원룸', '천호동원룸', '마포구원룸'];
const price = ['50만원', '60만원', '70만원'];
const data = [
  {
    products: '역삼동원룸',
    price: '50만원',
  },
  {
    products: '천호동원룸',
    price: '60만원',
  },
  {
    products: '마포구원룸',
    price: '70만원',
  },
];

const menus = ['Home', 'Product', 'About'];

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

  <div v-for="(item, index) in data" :key="index">
    <img src="./assets/vue.svg" alt="사진" class="room-img" />
    <strong style="display: block" @click="isModal = true">{{ item.products }}</strong>
    <p>{{ item.price }}</p>
    <button @click="count[0]++">허위매물 신고 버튼</button> <span>신고수 : {{ count[0] }}</span>
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
