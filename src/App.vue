<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>직방</h1>
    <div>
      <h2>xx원룸</h2>
      <p>{{ price1 }}만원</p>
    </div>
    <div>
      <h2>xx원룸</h2>
      <p>{{ price2 }}만원</p>
    </div>
  </div>
</template>

// 데이터바인딩 이유

<script>
export default {
  name: "App",
  data() {
    return {
      price1: 200,
      price2: 30,
    };
  },
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
  margin-top: 60px;
}
</style>
