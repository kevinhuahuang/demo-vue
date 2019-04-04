<template>
  <div id="app">
    <!--<Computed></Computed>-->
    <!--<StyleBind></StyleBind>-->
    <!--<ClassBind></ClassBind>-->
    <!--<Vif></Vif>-->
    <!--<Vfor></Vfor>-->
    <!--<Von></Von>-->
    <!--<Vmodel></Vmodel>-->
    <SlotParent></SlotParent>
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
import Vmodel from './components/base/Vmodel'
import SlotParent from './components/base/SlotParent'
export default {
  name: 'App',
  components: {SlotParent, Vmodel, Von, Vfor, Vif, ClassBind, StyleBind, Computed}
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
