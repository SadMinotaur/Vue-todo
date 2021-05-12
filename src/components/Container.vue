<template>
  <div>
    <div id="cards">
      <Card
        v-model="mes"
        v-for="item in array"
        v-on:delete="removeCard(item.key)"
        :key="item.key"
        :info="item"
      />
    </div>
    <div>
      <input v-model="mes" class="input" type="text" placeholder="Add task" />
    </div>
    <button class="input" v-on:click="addCard">Add task</button>
  </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Container",
  components: {
    Card,
  },
  data() {
    return { array: [], mes: "" };
  },
  methods: {
    addCard() {
      this.array = [
        ...this.array,
        { key: Symbol(), message: this.mes, date: new Date() },
      ];
      this.mes = "";
    },
    removeCard(key) {
      this.array = this.array.filter((i) => key !== i.key);
    },
  },
};
</script>

<style scoped>
#cards {
  margin: 15px;
  overflow-y: auto;
  height: 300px;
  border: 1px solid black;
  border-radius: 10px;
  display: flex;
  flex-wrap: wrap;
}
.input {
  border: 1px solid black;
  border-radius: 5px;
  height: 25px;
  width: 200px;
  margin: 5px;
  background: white;
}
</style>
