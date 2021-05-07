<template>
 <the-todos></the-todos>
</template>

<script>
import TheTodos from "./components/TheTodos.vue";

export default {
  components: {
    TheTodos,
  },
};
</script>

<style lang="scss">
body {
  background-color: #ffffff;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  color: rgb(65, 64, 64);
  #app {
    max-width: 650px;
    margin: auto;
    padding: 2rem;
  }
}
</style>