<template>
  <div id="app">
    <div class="app-logo">
      <img alt="Vue logo" src="./assets/logo.png">
    </div>
    <Home msg="VUE JS Simple Notes App by Squad 4"/>
  </div>
</template>

<script>
import Home from './views/Home';

export default {
  name: 'App',
  components: {
    Home
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
  margin-top: 10px;
}

.app-logo {
  text-align: center;
}
</style>
