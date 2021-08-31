<template>
  <div>
    <img :src="onroom.image" class="onroom_img" />
    <h2 @click="$emit('openModal', onroom.id)">{{ onroom.title }}</h2>
    <p>{{ onroom.price }}원</p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    onroom: Object,
  },
};
</script>

<style></style>
