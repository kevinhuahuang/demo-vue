<template>
  <div id="app">
    <!--<Computed></Computed>-->
    <StyleBind></StyleBind>
    <!--<img src="./assets/logo.png">-->
    <!--<router-view/>-->
  </div>
</template>

<script>
import Computed from './components/base/Computed'
import StyleBind from './components/base/StyleBind'
export default {
  name: 'App',
  components: {StyleBind, Computed}
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
