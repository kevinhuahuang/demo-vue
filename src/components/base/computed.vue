<template>
  <div>
    <p>鸡和兔子在一个圈子里</p>
    <label>头有<input type="text" v-model="headNum"/>只</label>
    <label style="display: block">脚有<input type="text" v-model="feetNum"/>只</label>
    <p>于是： </p>
    <p>兔子多少只：  {{rabbitNum}}</p>
    <p>鸡多少只：  {{chickenNum}}</p>
    <p>兔子比鸡多了 {{getSubtract()}} 只</p>
  </div>
</template>
/*************************************************************************************
computed:  对于任何复杂逻辑，都应该使用计算属性
1、computed是属性调用，后面没有小括号
2、有缓存功能，为什么要缓存：假设我们有一个性能开销比较大的计算属性 A，它需要遍历一个巨大的数组并做大量的计算。
然后我们可能有其他的计算属性依赖于 A ，当依赖值不改变，并不会执行computed的getter,而是直接返回缓存值。
如果没有缓存，我们将不可避免的多次执行 A 的 getter
*/
/*************************************************************************************
method:
1、method是函数调用，后面有小括号
2、没有缓存功能，每次调用都会执行，而computed只有在依赖值更新了才会执行
*/
<script>
export default {
  name: 'computed',
  data () {
    return {
      headNum: 18,
      feetNum: 52
    }
  },
  computed: { // 对于任何复杂逻辑，都应该使用计算属性
    // computed是属性调用，有缓存功能
    // 为什么要缓存：假设我们有一个性能开销比较大的计算属性 A，它需要遍历一个巨大的数组并做大量的计算。
    // 然后我们可能有其他的计算属性依赖于 A 。如果没有缓存，我们将不可避免的多次执行 A 的 getter
    rabbitNum: {
      get () { // 当feetNum, headNum数据改变才会触发计算，并渲染，否则直接返回缓存值
        return (this.feetNum - this.headNum * 2) / 2
      },
      set (value) {
        // 当rabbitNum值改变时触发
      }
    },
    chickenNum: {
      get () {
        return this.headNum - this.rabbitNum // 依赖computed中的rabbitNum
      }
    }
  },
  methods: {
    // method是函数调用，没有缓存功能
    getSubtract () {
      return this.rabbitNum - this.chickenNum
    }
  }
}
</script>

<style scoped>

</style>
