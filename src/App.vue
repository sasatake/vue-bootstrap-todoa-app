<template>
  <div id="main">
    <Header />
    <Todo />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Todo from "./components/Todo.vue";

export default {
  name: "App",
  components: {
    Header,
    Todo,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
