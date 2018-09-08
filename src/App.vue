<template>
  <div id="app">
    <Colorslider/>
  </div>
</template>

<script>
import Colorslider from "./components/Colorslider.vue";

export default {
  name: "app",
  components: {
    Colorslider
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
