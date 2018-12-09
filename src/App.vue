<template>
  <div id="app">
    <img class="logo" src="./assets/mortifier-logo.svg">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
}
.logo {
  width: 500px;
  position: absolute;
  top:10px;
  left: calc(50% - 250px);
}
</style>
