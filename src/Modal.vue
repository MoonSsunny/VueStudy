<template>
  <div class="black-bg " v-if="isModalOpen === true">
    <div class="white-bg">
      <h4>{{ onroom[isClick].title }}</h4>
      <p>{{ onroom[isClick].content }}</p>
      <!-- <input type="text" @input="month = $event.target.value" /> -->
      <input v-model="month" />
      <p>{{ month }}개월 : {{ onroom[isClick].price * month }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: {
    onroom: Array,
    isModalOpen: Boolean,
    isClick: Number,
  },
  data() {
    return {
      month: 1,
    };
  },
  watch: {
    month(data) {
      data >= 13 ? alert("13이상은 불가합니다") : null;
      isNaN(data)===true ? alert('글자는 불가합니다') : null;
    },
  },
  components: {},
};
</script>

<style></style>
