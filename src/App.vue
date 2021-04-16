<template>
  <div id="app">
    <tweets-section />
    <!-- uses the component TweetsSection in HTML -->
  </div>
</template>

<script>
//imports the component TweetsSection
import TweetsSection from "./components/TweetsSection.vue";

export default {
  name: "App",
  components: {
    TweetsSection,
    //registering the component TweetsSection
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
  margin-top: 60px;
}
</style>
