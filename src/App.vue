<template>
  <div id="app">
    <div class="align-middle">
      <BaseTimer />
    </div>
  </div>
</template>

<script>
import BaseTimer from "./components/BaseTimer.vue";

export default {
  name: "App",
  components: {
    BaseTimer,
  },
};
</script>

<style>
body {
  background: #058f8c;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.align-middle {
  margin: auto;
  width: 50%;
}
</style>
