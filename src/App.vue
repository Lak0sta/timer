<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Timer
      :initialValue="100"
    />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Timer from './components/Timer.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Timer,
  }
}
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
