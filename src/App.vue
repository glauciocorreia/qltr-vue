<template>
  <div id="app">
    <Navbar></Navbar>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    Navbar,
    HelloWorld
  }
}
</script>

<style lang="scss">

@import 'assets/scss/reset.css';
@import 'assets/scss/style.scss'

</style>
