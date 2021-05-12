<template>
  <div @click="$emit('delete')" class="card">
    <div>{{ message }}</div>
    <div>{{ hour + " : " + minute }}</div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["delete", "info"],
  data() {
    const props = this.info;
    const min = props.date.getMinutes();
    return {
      message: props.message,
      hour: props.date.getHours(),
      minute: min > 9 ? min : "0" + min,
    };
  },
};
</script>

<style scoped>
.card {
  text-align: start;
  padding: 3px;
  border-radius: 5px;
  margin: 5px;
  border: 1px solid black;
  height: 80px;
  min-width: 150px;
}
</style>
