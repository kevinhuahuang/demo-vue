<template>
  <div>
    <!---->
    <div>
      <label><input type="checkbox" v-model="isCat"/>猫</label>
      <label><input type="checkbox" v-model="isDog"/>狗</label><!--isDog绑定计算属性-->
      <div v-if="isCat" style="font-size: 3rem">猫</div>
      <!--v-if的值为表达式-->
      <div v-if="!isCat" style="font-size: 3rem">狗</div>
    </div>
    <p>------------------------------------------------------------------------------------</p>
    <!-- 在<template> 元素上使用 v-if 条件渲染分组-->
    <div>
      <label><input type="radio" v-model="sex" value="man"/>男</label><!--isDog绑定计算属性-->
      <label><input type="radio" v-model="sex" value="woman"/>女</label><!--isDog绑定计算属性-->
      <template v-if="sex === 'man'">
        <p>男人说：</p>
        <p>男人是天</p>
      </template>
      <template v-if="sex === 'woman'">
        <p>女人说：</p>
        <p>女人是地</p>
      </template>
    </div>
    <p>------------------------------------------------------------------------------------</p>
    <!-- v-if 与 v-else-->
    <div>
      <label>是人<input type="checkbox" v-model="isHuman">还是兽</label>
      <div v-if="isHuman"><p>人</p></div>
      <div v-else><p>兽</p></div>
    </div>
    <p>------------------------------------------------------------------------------------</p>
    <!-- 使用 key 来控制复用或不复用(默认复用) 相同的元素使用相同的key值将复用，使用不同的key值将不复用-->
    <!--元素复用，input在切换后内容不变-->
    <label>输入用户名<input type="checkbox" v-model="loginType">或邮箱地址</label>
    <div></div>
    <template v-if="loginType">
      <label>Username</label>
      <input placeholder="Enter your username">
    </template>
    <template v-else>
      <label>Email</label>
      <input placeholder="Enter your email address">
    </template>
  </div>
</template>

<script>
export default {
  name: 'Vif',
  data () {
    return {
      isCat: true,
      isMan: true,
      sex: 'man',
      isHuman: true,
      loginType: true
    }
  },
  computed: {
    isDog: {
      get () {
        return !this.isCat
      },
      set (value) { // 注意，需要设置setter
        this.isCat = !value
      }
    }
  }
}
</script>

<style scoped>

</style>
