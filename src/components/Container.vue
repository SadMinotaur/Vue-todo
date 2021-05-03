<template>
  <div>
    <Card v-for="item in testArray" :key="item.message" name="test" />
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Container",
  components: {
    Card,
  },
  data: () => ({ testArray: [{ message: "1" }, { message: "2" }] }),
};
</script>

<style scoped>
</style>
