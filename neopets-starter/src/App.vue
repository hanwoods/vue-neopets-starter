<template>
  <div id="app">
    <WelcomePage header_msg="Welcome to one45's neopets!" sub_msg="Please pick a character to begin"/>
  </div>
</template>

<script>
import WelcomePage from './components/WelcomePage.vue'

export default {
  name: 'app',
  components: {
    WelcomePage
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
