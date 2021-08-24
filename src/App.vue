<template>
  <div id="app">
    <div class="black-bg " v-if="isModalOpen === ture">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>상세페이지내용임</p>
        <button @click="isModalOpen = false">닫기</button>
      </div>
    </div>
    <div class="menu">
      <a v-for="(menu, index) in menus" :key="index" href="#">{{ menu }}</a>
    </div>
    <h1>원룸샵</h1>
    <button @click="isModalOpen = ture">모달오픈</button>
    <div v-for="(notice, i) in onroom" :key="i">
      <img :src="notice.image" />
      <h2 class="red">{{ notice.title }}</h2>
      <p>{{ notice.price }}</p>
    </div>
  </div>
</template>

<script>
import data from "./data.js";
export default {
  name: "App",
  data() {
    return {
      신고수: [0, 0, 0],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Product", "About"],
      isModalOpen: false,
      onroom: data,
    };
  },
  methods: {},
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
  text-decoration: none;
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
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
