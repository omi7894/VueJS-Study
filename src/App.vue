<template>
  <div class="black-bg" v-if="show">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="show = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="item in menu" :key="item">{{ item }}</a>
  </div>

  <div>
    <img :src="products[0].image" class="room-img" />
    <h4 @click="show = true">{{ products[0].title }}</h4>
    <p>{{ products[0].price }}</p>
    <button @click="num[0]++">허위매물신고</button>
    <span>신고수 : {{ num[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg " class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>50만원</p>
    <button @click="increase2">허위매물신고</button>
    <span>신고수 : {{ num[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg " class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>50만원</p>
    <button @click="increase3">허위매물신고</button>
    <span>신고수 : {{ num[2] }}</span>
  </div>
</template>

<script>
import datas from "./assets/data.js";

export default {
  name: "App",
  data() {
    return {
      show: false,
      menu: ["Home", "Shop", "About"],
      oldProducts: ["역삼동원룸", "잠실원룸", "마포구원룸"],
      products: datas,
      num: [0, 0, 0],
    };
  },
  methods: {},
  components: {},
};
</script>

<style>
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
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
