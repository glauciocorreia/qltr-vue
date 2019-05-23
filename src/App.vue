<template>
  <div id="app">
    <div>
      <Navbar></Navbar>
      <HomeBody
        subtitle="WHAT WE DO?"
        title1="We grow"
        title2="great business"
        textLink="Velit laoreet id donec ultrices. Ut lectus arcu bibendum varius."
      ></HomeBody>
      <!-- <img alt="Vue logo" src="./assets/logo.png">
      <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import HomeBody from "./components/HomeBody.vue";
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    Navbar,
    HomeBody,
    HelloWorld
  }
};
</script>

<style lang="scss">
@import "assets/scss/reset.css";
@import "assets/scss/style.scss";
</style>
