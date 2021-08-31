<template>
  <div id="app">
    <Modal
      @closeModal="isModalOpen = false"
      :onroom="onroom"
      :isClick="isClick"
      :isModalOpen="isModalOpen"
    />
    <div class="menu">
      <a v-for="(lists, i) in list" :key="i" href="#">{{ lists }}</a>
    </div>
    <Discount />
    <!-- <div
      v-for="(notice, i) in onroom"
      :key="i"
      @click="
        isModalOpen = ture;
        isClick = i;
      "
    >
      <img :src="notice.image" class="onroom_img" />
      <h2 class="red">{{ notice.title }}</h2>
      <p>{{ notice.price }}원</p>
    </div> -->
    <button @click="priceSort">가격순 정렬</button>
    <button @click="sortBack">되돌리기</button>
    <Card
      @openModal="
        isModalOpen = true;
        isClick = $event;
      "
      :onroom="onroom[i]"
      v-for="(room, i) in onroom"
      :key="i"
    />
  </div>
</template>

<script>
import data from "./data.js";
import Discount from "./Discount.vue";
import Modal from "./Modal.vue";
import Card from "./Card.vue";

export default {
  name: "App",
  data() {
    return {
      isModalOpen: false,
      onroomOriginal: [...data],
      onroom: data,
      isClick: 0,
      list: ["home", "price", "about"],
      showDiscount: true,
    };
  },
  methods: {
    priceSort(){
      this.onroom.sort((a,b)=>b.price-a.price)
    },
    sortBack(){
      this.onroom = [...this.onroomOriginal];
    }
  },

  components: {
    Discount,
    Modal,
    Card,
  },
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
.onroom_img {
  width: 400px;
  border-radius: 8px;
}
</style>
