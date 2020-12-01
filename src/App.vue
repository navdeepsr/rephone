<template>
  <div id="app">
    <Profiles />
  </div>
</template>

<script>
import Profiles from "./components/Profiles.vue";

export default {
  name: "App",
  components: { Profiles },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #f3f5fa;
  color: #2c3e58;
  min-height: 600px;
}
</style>
