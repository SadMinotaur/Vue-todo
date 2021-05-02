<template>
  <div id="app">
    <div id="mainWindow">
      <Header msg="Todo" />
      <Container />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Container from "./components/Container.vue";

export default {
  name: "App",
  components: {
    Header,
    Container,
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

#mainWindow {
  margin: 15px;
  border: 1px solid black;
  border-radius: 10px;
}
</style>
