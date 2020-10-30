<template>
  <div id="app">
<!--    <img alt="Vue logo" src="./assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Home />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Home from "@/components/home";

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>

</style>
