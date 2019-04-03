<template>
  <div id="app">
    <!--<Computed></Computed>-->
    <!--<StyleBind></StyleBind>-->
    <!--<ClassBind></ClassBind>-->
    <!--<Vif></Vif>-->
    <!--<Vfor></Vfor>-->
    <Von></Von>
    <!--<img src="./assets/logo.png">-->
    <!--<router-view/>-->
  </div>
</template>

<script>
import Computed from './components/base/Computed'
import StyleBind from './components/base/StyleBind'
import ClassBind from './components/base/ClassBind'
import Vif from './components/base/Vif'
import Vfor from './components/base/Vfor'
import Von from './components/base/Von'
export default {
  name: 'App',
  components: {Von, Vfor, Vif, ClassBind, StyleBind, Computed}
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
